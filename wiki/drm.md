DRM is not used for every stream. In tests with the web client, stereo tracks up to HI_RES_LOSSLESS were delivered without `ContentProtection` (see [PlaybackInfo](track-playbackinfo)). The official API returns the license urls in `drmData` of [TrackManifests](official-trackManifests).

### Widevine License (endpoint verified 2026-11)
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
