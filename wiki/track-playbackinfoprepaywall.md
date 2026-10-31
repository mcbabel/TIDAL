#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/playbackinfoprepaywall?countryCode={country}&audioquality={enum}&playbackmode={enum}&assetpresentation={enum}```
##### audioQuality Enums
```LOW```(64kbps 22.05kHz MP3)
##### playbackmode Enums
```STREAM```
##### assetPresentation Enums
```PREVIEW```
##### Header
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "trackId": 38519997,
  "assetPresentation": "PREVIEW",
  "audioMode": "STEREO",
  "audioQuality": "LOW",
  "manifestMimeType": "application/vnd.tidal.bts",
  "manifest": "Base64 Encoded"
}
```
#### Definition
 + manifestMimeType: application/vnd.tidal.bts (DIRECT STREAM)
 + manifest (Base64 Encoded)

#### Example Decoded vnd.tidal.bts Manifest
``` yaml
{"mimeType":"audio/mpeg","codecs":"mp3","encryptionType":"NONE","urls":["https://ab-pr-fa.audio.tidal.com/something"]}
```

#### Update 2026-11 (verified with user token)
* With a user token the endpoint returns a PREVIEW in the requested quality (e.g. LOSSLESS as `application/dash+xml`, FLAC) and additionally `previewReason` (e.g. `FULL_REQUIRES_SUBSCRIPTION`), `manifestHash`, the ReplayGain fields, `bitDepth` and `sampleRate`.
