DRM is not used for every stream. In tests with the web client, stereo tracks up to HI_RES_LOSSLESS were delivered without `ContentProtection` (see [PlaybackInfo](track-playbackinfo)). The official API returns the license urls in `drmData` of [TrackManifests](official-trackManifests).

### Widevine License (verified 2026-11)
* License server for Widevine protected DASH streams (Shaka Player config: `servers: {"com.widevine.alpha": "https://api.tidal.com/v2/widevine"}`). Body: the binary license challenge of the CDM. Robustness `SW_SECURE_CRYPTO`.
* Replaces the old `POST drm/licenses/widevine`.
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/widevine```
##### Header
```authorization: Bearer {access_token}```

### FairPlay (from web player code 2026-11, not executed: needs Safari)
* Certificate: `GET https://fp.fa.tidal.com/certificate`. Used for Safari (`com.apple.fps.1_0`).
##### Method
```POST```
##### Url
```https://fp.fa.tidal.com/license```
##### Header
```authorization: Bearer {access_token}```

#### Update 2026-11: Test status
* **Widevine**: endpoint verified. An empty body answers `500 "Required request body is missing ... generateWidevineLicense..."`. A real license request needs a license challenge from a Widevine CDM for a DRM protected stream. All streams the test account received in the web player were not DRM protected, so there was no challenge to send.
* **FairPlay**: not tested. It only works in Safari with Apple's FairPlay CDM, which the test browser does not have.

#### Update 2026-11: Widevine verified (Google Chrome 156 with Widevine CDM)
Which streams are protected (verified 2026-11-01 with a Premium account):

| Source | DRM |
|---|---|
| Official API [`trackManifests`](official-trackManifests), full track (`trackPresentation: FULL`) | **Widevine for every format**: `FLAC_HIRES`, `FLAC`, `AACLC`, `HEAACV1` and `EAC3_JOC` (Dolby Atmos). The MPD has `ContentProtection` for CENC, Widevine (`urn:uuid:edef8ba9-79d6-4ace-a3c8-27dcd51d21ed`) and PlayReady (`urn:uuid:9a04f079-9840-4286-ab92-e65be0885f95`) with `cenc:pssh` and `cenc:default_KID`. |
| Official API, preview (`trackPresentation: PREVIEW`) | none |
| Private API [`playbackinfo`](track-playbackinfo) (web client) | none. Dolby Atmos tracks fall back to a stereo stream (`audioMode: STEREO`). |

The current web player plays through the official API, so it needs a browser with Widevine. Browsers without Widevine show `S6001` (Shaka `REQUESTED_KEY_SYSTEM_CONFIG_UNAVAILABLE`).

##### Service certificate
```POST https://api.tidal.com/v2/widevine```\
Header: ```Authorization: Bearer {access_token}```, ```Content-Type: application/octet-stream```\
Body: the Widevine service certificate request (2 bytes `0x08 0x04`)\
Response: `200`, `application/octet-stream`, 716 bytes (signed service certificate)

##### License
```POST https://api.tidal.com/v2/widevine```\
Header: ```Authorization: Bearer {access_token}```, ```Content-Type: application/octet-stream```\
Body: the license challenge created by the CDM from the Widevine `pssh` of the MPD (`MediaKeySession.generateRequest('cenc', pssh)`, 1708 bytes in the test)\
Response: `200`, `application/octet-stream`, 710 bytes. After `MediaKeySession.update(license)` the key status was `usable`.

* Works with the token of the official API and with the token of the private API (both `200`).
* Without token: `400 {"error":"invalid_request","description":"Token is missing","subStatus":11002}`.
* The license is only usable inside the CDM; keys cannot be read by the page.
* `drmData` of [`trackManifests`](official-trackManifests) names the same url as `licenseUrl` and `certificateUrl`.

#### Update 2026-11: Playback flow of the web player (verified, Widevine Chrome, logged in)
| Time | Request | Result |
|---|---|---|
| 0 ms | `POST https://tidal.com/v1/rt/connect` | WebSocket url ([Streaming Privileges](streaming-privileges)) |
| 38 ms | `GET https://openapi.tidal.com/v2/trackManifests/{id}?adaptive=true&formats=HEAACV1&formats=AACLC&formats=FLAC&formats=FLAC_HIRES&manifestType=MPEG_DASH&uriScheme=DATA&usage=PLAYBACK` | Widevine encrypted MPD |
| 393 ms | `POST https://api.tidal.com/v2/widevine` (1708 byte challenge) | `200`, license |
| 395 ms | WebSocket `wss://pushkin-v2.tidal.com/public/token/{token}/ws` | open |
| from ~0.4 s | segments from `sp-ad-fa.audio.tidal.com` | playback |
| 2.7 s, 17.7 s | `POST https://tidal.com/api/event-batch` | `200` (play log) |

The player does not request the service certificate separately; it sends the license challenge directly. The next track's manifest is requested ahead of time.

Logged out (preview): the same `trackManifests` call with the client credentials token returns an unencrypted preview, there is no license request, no `rt/connect`, and events go to `https://tidal.com/api/public/event-batch`.
