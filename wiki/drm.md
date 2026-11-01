DRM is not used for every stream. In tests with the web client, stereo tracks up to HI_RES_LOSSLESS were delivered without `ContentProtection` (see [PlaybackInfo](track-playbackinfo)). The official API returns the license urls in `drmData` of [TrackManifests](official-trackManifests).

### Widevine License (from web player code 2026-11, not live-tested)
* License server for Widevine protected DASH streams (Shaka Player config: `servers: {"com.widevine.alpha": "https://api.tidal.com/v2/widevine"}`). Body: the binary license challenge of the CDM. Robustness `SW_SECURE_CRYPTO`.
* Replaces the old `POST drm/licenses/widevine`.
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/widevine```
##### Header
```authorization: Bearer {access_token}```

### FairPlay (from web player code 2026-11, not live-tested)
* Certificate: `GET https://fp.fa.tidal.com/certificate`. Used for Safari (`com.apple.fps.1_0`).
##### Method
```POST```
##### Url
```https://fp.fa.tidal.com/license```
##### Header
```authorization: Bearer {access_token}```
