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

#### Update 2026-11 (verified with a Premium account)
* Full tracks are **Widevine encrypted for every format** (also stereo FLAC/AAC). Example `drmData`:
``` yaml
"drmData": {
  "drmSystem": "WIDEVINE",
  "licenseUrl": "https://api.tidal.com/v2/widevine",
  "certificateUrl": "https://api.tidal.com/v2/widevine"
}
```
* With `adaptive=true` the MPD contains all requested formats as one adaptive ladder, e.g. `FLAC_HIRES,44100,24`, `FLAC,44100,16`, `AACLC`, `HEAACV1`.
* Dolby Atmos: request `formats=EAC3_JOC` for an Atmos track. Atmos versions are separate albums/tracks with `audioModes: ["DOLBY_ATMOS"]` (e.g. track `187935270`). Result: one representation `EAC3_JOC`, `codecs="ec-3"`, about 769 kbps, 48 kHz, Widevine encrypted.
* The web player requests: `GET /trackManifests/{id}?adaptive=true&formats=HEAACV1&formats=AACLC&formats=FLAC&formats=FLAC_HIRES&manifestType=MPEG_DASH&uriScheme=DATA&usage=PLAYBACK` (formats as repeated parameters).
* Previews are not encrypted. See [DRM](drm) for the license request.
