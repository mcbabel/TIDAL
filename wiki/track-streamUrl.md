#### Example Request
* If you get the "Asset not ready for playback" response but the content is streamReady use the playbackinfopostpaywall endpoint.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/streamUrl?countryCode={country}&soundQuality={enum}```
##### soundQuality Enums
```LOW```(96kbps AAC)\
```HIGH```(320kbps AAC)\
```LOSSLESS```(1411kbps|16bit/44.1kHz FLAC/ALAC)\
```HI_RES```(24bit/96kHz MQA encoded FLAC)

##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "url": "http://sp-pr-fa.audio.tidal.com/mediatracks/something",
  "trackId": 38519997,
  "playTimeLeftInMinutes": -1,
  "soundQuality": "LOSSLESS",
  "encryptionKey": "",
  "codec": "FLAC"
}
```

#### Update 2026-11 (verified)
* Deprecated. Answers `401 {"status":401,"subStatus":4005,"userMessage":"Asset is not ready for playback"}` for tracks. Use [PlaybackInfo](track-playbackinfo).
* The same applies to `GET tracks/{id}/urlpostpaywall?audioquality={enum}&urlusagemode=STREAM&assetpresentation=FULL`.
* `soundQuality=HI_RES` is deprecated, see [Audio Quality](AudioQuality).
