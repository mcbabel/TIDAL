#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/mixes/{mixId}/items?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response (shortened)

``` yaml
{
  "limit": 40,
  "offset": 0,
  "totalNumberOfItems": 40,
  "items": [
    {
      "item": {
        "id": 36534567,
        "title": "One Percent",
        "duration": 335,
        "replayGain": -4.41,
        "peak": 0.988586,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2014-10-20T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 5,
        "volumeNumber": 1,
        "version": null,
        "popularity": 13,
        "copyright": "Gondwana Records",
        "url": "http://www.tidal.com/track/36534567",
        "isrc": "GBVTB1409005",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 4764457,
          "name": "GoGo Penguin",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 4764457,
            "name": "GoGo Penguin",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 36534562,
          "title": "v2.0 (Deluxe Edition)",
          "cover": "be3baeee-a015-424e-a6c1-64ca3fc0f45d",
          "videoCover": null
        },
        "mixes": {
          "TRACK_MIX": "00119ea4c58b8f337eda950ef30fae"
        }
      },
      "type": "track"
    },
    {
      "item": {
        "id": 33393818,
        "title": "Mansions of Millions of Years",
        "duration": 367,
        "replayGain": -5.09,
        "peak": 0.978088,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2014-09-15T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 1,
        "volumeNumber": 1,
        "version": null,
        "popularity": 4,
        "copyright": "2014 Gondwana Records",
        "url": "http://www.tidal.com/track/33393818",
        "isrc": "GBVTB1411001",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 5899631,
          "name": "Mammal Hands",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 5899631,
            "name": "Mammal Hands",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 33393817,
          "title": "Animalia",
          "cover": "9f736026-9663-41b0-9035-78f9245aa1e1",
          "videoCover": null
        },
        "mixes": {
          "TRACK_MIX": "001c4bcea2ec7ee0d7f2a0c0585d39"
        }
      },
      "type": "track"
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (also with `x-tidal-token`). Mix ids change over time. Get the current id from the `mixes` field of a track (`TRACK_MIX`) or artist (`ARTIST_MIX`), or from [Get Track Mix](track-mix) / [Get Artist Mix](artist-mix).
