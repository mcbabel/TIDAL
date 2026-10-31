#### Example Request (verified 2026-11)
* Current playback endpoint of the TIDAL apps. Same parameters and response as [playbackinfopostpaywall](track-playbackinfopostpaywall).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/playbackinfo?countryCode={country}&audioquality={enum}&playbackmode={enum}&assetpresentation={enum}```
##### audioQuality Enums
```LOW```(96kbps HE-AAC)\
```HIGH```(320kbps AAC-LC)\
```LOSSLESS```(16bit/44.1kHz FLAC)\
```HI_RES_LOSSLESS```(up to 24bit/192kHz FLAC)
##### playbackmode Enums
```STREAM```\
```OFFLINE```
##### assetPresentation Enums
```FULL```\
```PREVIEW```
##### Optional Url Parameter
```streamingsessionid={uuid}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "trackId": 38519997,
  "assetPresentation": "FULL",
  "audioMode": "STEREO",
  "audioQuality": "HI_RES_LOSSLESS",
  "manifestMimeType": "application/dash+xml",
  "manifestHash": "XsU6XORbrWQ0FLLhvliVLpKaz6qYDqrQOzQF3Jf8jCE=",
  "manifest": "Base64 Encoded",
  "albumReplayGain": -5.41,
  "albumPeakAmplitude": 0.980679,
  "trackReplayGain": -4.64,
  "trackPeakAmplitude": 0.906234,
  "bitDepth": 24,
  "sampleRate": 44100
}
```
#### Definition
 + manifestMimeType: application/dash+xml (MPEG DASH) | application/vnd.tidal.bts (DIRECT STREAM)
 + manifest (Base64 Encoded)
 + manifestHash: hash of the manifest
 + albumReplayGain, albumPeakAmplitude, trackReplayGain, trackPeakAmplitude: loudness normalization
 + bitDepth, sampleRate: only for LOSSLESS and HI_RES_LOSSLESS
 + previewReason: only for previews (e.g. `FULL_REQUIRES_SUBSCRIPTION`)

#### Example Decoded application/dash+xml Manifest (HI_RES_LOSSLESS, URLs shortened)
``` xml
<?xml version='1.0' encoding='UTF-8'?><MPD xmlns="urn:mpeg:dash:schema:mpd:2011" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:cenc="urn:mpeg:cenc:2013" xsi:schemaLocation="urn:mpeg:dash:schema:mpd:2011 DASH-MPD.xsd" profiles="urn:mpeg:dash:profile:isoff-main:2011" type="static" minBufferTime="PT3.993S" mediaPresentationDuration="PT2M4.073S"><Period id="0"><AdaptationSet id="0" contentType="audio" mimeType="audio/mp4" lang="und" group="main" segmentAlignment="true"><Role schemeIdUri="urn:mpeg:dash:role:2011" value="main"/><Representation id="FLAC_HIRES,44100,24" codecs="flac" bandwidth="1227913" audioSamplingRate="44100"><AudioChannelConfiguration schemeIdUri="urn:mpeg:dash:23003:3:audio_channel_configuration:2011" value="2"/><SegmentTemplate timescale="44100" initialization="https://sp-ad-fa.audio.tidal.com/…" media="https://sp-ad-fa.audio.tidal.com/…" startNumber="1"><SegmentTimeline><S d="176128" r="30"/><S d="11652"/></SegmentTimeline></SegmentTemplate></Representation></AdaptationSet></Period></MPD>
```
All qualities (LOW to HI_RES_LOSSLESS) were delivered as MPEG DASH with fragmented MP4 segments to the web client. Segment URLs are signed and expire.
