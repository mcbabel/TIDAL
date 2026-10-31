TIDAL removed MQA and Sony 360 Reality Audio in 2024. Hi-Res is now plain FLAC (up to 24bit/192kHz).

##### audioQuality Enums (Update 2026-11)
```LOW```(96kbps HE-AAC)\
```HIGH```(320kbps AAC-LC)\
```LOSSLESS```(16bit/44.1kHz FLAC)\
```HI_RES_LOSSLESS```(up to 24bit/192kHz FLAC)\
~~```HI_RES```~~(24bit/96kHz MQA encoded FLAC, deprecated: requests with HI_RES are answered with HI_RES_LOSSLESS)

The response contains the quality you actually get (it can be lower than requested). Use `audioQuality`, `bitDepth` and `sampleRate` of the [PlaybackInfo](track-playbackinfo) response.

##### Measured 2026-11-01 (web client, track 38519997)
| Requested | audioQuality | codecs | bandwidth | bitDepth / sampleRate |
|---|---|---|---|---|
| LOW | LOW | mp4a.40.5 | 96974 | – |
| HIGH | HIGH | mp4a.40.2 | 322151 | – |
| LOSSLESS | LOSSLESS | flac | 525992 | 16 / 44100 |
| HI_RES_LOSSLESS | HI_RES_LOSSLESS | flac | 1227913 | 24 / 44100 |
| HI_RES | HI_RES_LOSSLESS | flac | 1227913 | 24 / 44100 |

##### audioMode Enums
```STEREO```\
```DOLBY_ATMOS```\
~~```SONY_360RA```~~ (removed)

##### mediaMetadata Tags
Tracks and albums have a `mediaMetadata.tags` field listing the available qualities: ```LOSSLESS```, ```HIRES_LOSSLESS```, ```DOLBY_ATMOS```
``` yaml
"audioQuality": "LOSSLESS",
"audioModes": [
  "STEREO"
],
"mediaMetadata": {
  "tags": [
    "LOSSLESS",
    "HIRES_LOSSLESS"
  ]
}
```
`audioQuality` of catalog items stays `LOSSLESS` even if Hi-Res is available. Use `mediaMetadata.tags`.

##### videoQuality Enums
```AUDIO_ONLY```\
```LOW```\
```MEDIUM```\
```HIGH```

##### Subscription
[Get User Subscription](user-subscription) → `highestSoundQuality`. Since 2024 the subscription types are `FREE` and `PREMIUM` (old: `HIFI`, `HIFI_PLUS`).

##### Official API
The [Official TIDAL API](OfficialAPI) uses formats instead: ```HEAACV1```, ```AACLC```, ```FLAC```, ```FLAC_HIRES```, ```EAC3_JOC``` (Dolby Atmos), see [Get TrackManifest](official-trackManifests).
