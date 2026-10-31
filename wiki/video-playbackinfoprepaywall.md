#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/playbackinfoprepaywall?countryCode={country}&videoquality={enum}&playbackmode={enum}&assetpresentation={enum}```
##### videoquality Enums
```LOW```(640x360 1116kbps MP4)
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
{"mimeType":"video/mp4","codecs":"avc1.42001e,mp4a.40.2","encryptionType":"NONE","urls":["https://vb-pr-fa.video.tidal.com/something"]}
```