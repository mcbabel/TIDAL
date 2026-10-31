#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/playbackinfopostpaywall?countryCode={country}&videoquality={enum}&playbackmode={enum}&assetpresentation={enum}```
##### videoQuality Enums
```AUDIO_ONLY```\
```LOW```\
```MEDIUM```\
```HIGH```
##### playbackmode Enums
```STREAM```\
```OFFLINE```
##### assetPresentation Enums
```FULL```\
```PREVIEW```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "videoId": 53654641,
  "streamType": "ON_DEMAND",
  "assetPresentation": "FULL",
  "videoQuality": "HIGH",
  "manifestMimeType": "application/vnd.tidal.emu",
  "manifest": "Base64 Encoded"
}
```
#### Definition
 + manifestMimeType: application/vnd.tidal.bts (DIRECT STREAM)
 + manifest (Base64 Encoded)

#### Example Decoded application/vnd.tidal.bts Manifest
``` yaml
{"mimeType":"application/vnd.apple.mpegurl","urls":["http://api.tidal.com/v1/videos/53654641/hls/something"]}
```

#### Update 2026-11 (verified)
* Still works. `GET videos/{id}/playbackinfo` is an alias with the same parameters and response.
* The response additionally contains `manifestHash`.
* The decoded `application/vnd.tidal.emu` manifest is JSON: `{"mimeType":"application/vnd.apple.mpegurl","urls":["https://im-fa.manifest.tidal.com/1/manifests/....m3u8?..."]}` (HLS).
