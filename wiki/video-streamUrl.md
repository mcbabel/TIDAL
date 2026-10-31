#### Example Request
* If you get the "Asset not ready for playback" response but the content is streamReady use the playbackinfopostpaywall endpoint.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/streamUrl?countryCode={country}&videoQuality={enum}```
##### videoQuality Enums
```AUDIO_ONLY```(96kbps MP4)\
```HIGH```(MP4)

##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "url": "http://api.tidal.com/v1/videos/53654641/hls/something",
  "videoQuality": "HIGH"
}
```

#### Update 2026-11 (verified)
* Still works for videos and returns an HLS playlist url on `im-fa.manifest.tidal.com`:
``` yaml
{
  "url": "https://im-fa.manifest.tidal.com/1/manifests/xxxxxxxx.m3u8?xxxxxxxx",
  "videoQuality": "HIGH"
}
```
* Alternative: `GET videos/{id}/urlpostpaywall?videoquality={enum}&urlusagemode=STREAM&assetpresentation=FULL` returns `{"urls":["https://im-fa.manifest.tidal.com/...m3u8?..."],"videoId":75623239,"assetPresentation":"FULL","videoQuality":"HIGH","streamingSessionId":null,"format":"HLS"}`
