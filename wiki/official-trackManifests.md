#### Example Request (verified 2026-11)
* Playback manifest of the Official API (equivalent of [PlaybackInfo](track-playbackinfo))
* With a Client Credentials token or without subscription you get a PREVIEW (`previewReason: FULL_REQUIRES_SUBSCRIPTION`)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackManifests/{trackId}?manifestType={enum}&formats={enums}&uriScheme={enum}&usage={enum}&adaptive={bool}```
##### manifestType Enums
```HLS```\
```MPEG_DASH```
##### formats Enums (comma separated)
```HEAACV1```\
```AACLC```\
```FLAC```\
```FLAC_HIRES```\
```EAC3_JOC``` (Dolby Atmos)
##### uriScheme Enums
```HTTPS``` (uri is a link to the manifest)\
```DATA``` (uri is a `data:` url with the base64 manifest)
##### usage Enums
```PLAYBACK```\
```DOWNLOAD```
##### Header
```Authorization: Bearer {access_token}```\
```Accept: application/vnd.api+json```
#### Example Response

``` yaml
{
  "data": {
    "id": "38519997",
    "type": "trackManifests",
    "attributes": {
      "trackPresentation": "PREVIEW",
      "previewReason": "FULL_REQUIRES_SUBSCRIPTION",
      "uri": "data:application/dash+xml;base64,PD94bWwgdmVyc2lvbj0nMS4wJyBlbmNvZGluZz0nVVRGLTg...",
      "hash": "XWnmep92BXmSx+eZU/w8ffdCEBvdrvrEbnjKhAEYESU=",
      "formats": [
        "HEAACV1",
        "AACLC",
        "FLAC",
        "FLAC_HIRES"
      ],
      "albumAudioNormalizationData": {
        "replayGain": -5.41,
        "peakAmplitude": 0.980679
      },
      "trackAudioNormalizationData": {
        "replayGain": -4.64,
        "peakAmplitude": 0.906234
      }
    }
  },
  "links": {
    "self": "/trackManifests/38519997?uriScheme=DATA&adaptive=true&formats=AACLC%2CFLAC%2CFLAC_HIRES%2CHEAACV1&usage=PLAYBACK&manifestType=MPEG_DASH"
  }
}
```
#### Definition
 + trackPresentation: `FULL` | `PREVIEW`
 + previewReason: `FULL_REQUIRES_SUBSCRIPTION` | `FULL_REQUIRES_PURCHASE` | `FULL_REQUIRES_HIGHER_ACCESS_TIER`
 + drmData (only if DRM protected): `drmSystem` (`WIDEVINE` | `FAIRPLAY`), `licenseUrl`, `certificateUrl`, `initData`
 + Videos: `GET /videoManifests/{videoId}?uriScheme={enum}&usage={enum}`
