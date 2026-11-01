#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/playlists/{id}/recommendations/items?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 200,
  "items": [
    {
      "item": {
        "id": 31706292,
        "title": "King Bromeliad",
        "duration": 532,
        "replayGain": -7.12,
        "peak": 0.97525,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2014-06-23T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 1,
        "volumeNumber": 1,
        "version": null,
        "popularity": 6,
        "copyright": "2014 Eglo Records",
        "description": null,
        "url": "http://www.tidal.com/track/31706292",
        "isrc": "GB4HG1300124",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3714298,
          "name": "Floating Points",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3714298,
            "name": "Floating Points",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 31706291,
          "title": "King Bromeliad / Montparnasse",
          "cover": "30feb835-7600-4f40-bad5-03d07acdf6d0",
          "videoCover": null,
          "releaseDate": "2014-06-23"
        },
        "mixes": {
          "TRACK_MIX": "00178a4a278475df81ddcbf40b7ed5"
        }
      },
      "type": "track"
    },
    {
      "item": {
        "id": 13244375,
        "title": "Beau Mot Plage",
        "duration": 406,
        "replayGain": -6.63,
        "peak": 1.0,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2016-06-05T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 4,
        "volumeNumber": 1,
        "version": null,
        "popularity": 5,
        "copyright": "2011 PAMPA RECORDS",
        "description": null,
        "url": "http://www.tidal.com/track/13244375",
        "isrc": "DEMM11100017",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3599950,
          "name": "Isolée",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3599950,
            "name": "Isolée",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 13244371,
          "title": "Rest",
          "cover": "0584b5b8-89e3-4bd3-9ebb-0d49a5b2204a",
          "videoCover": null,
          "releaseDate": "2000-01-01"
        },
        "mixes": {
          "TRACK_MIX": "001a13e2e0c1673144abb06dbe43ae"
        }
      },
      "type": "track"
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
Needs a user token (`401` with `x-tidal-token` only).
