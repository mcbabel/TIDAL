#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items?countryCode={country}&limit=2```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 17,
  "items": [
    {
      "item": {
        "id": 143107918,
        "title": "Kora",
        "duration": 335,
        "replayGain": -6.15,
        "peak": 0.999983,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2020-06-12T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 6,
        "volumeNumber": 1,
        "version": null,
        "popularity": 10,
        "copyright": "℗ 2020 Decca Records France",
        "description": null,
        "url": "http://www.tidal.com/track/143107918",
        "isrc": "FRUM72000183",
        "editable": false,
        "explicit": false,
        "audioQuality": "HI_RES",
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
          "id": 143107912,
          "title": "GoGo Penguin",
          "cover": "a4a29cd1-eef9-4e8f-b827-85d3b5c4b428",
          "videoCover": null,
          "releaseDate": "2020-06-12"
        },
        "mixes": {
          "MASTER_TRACK_MIX": "014a7cd9604d27443e913e25ecf97f",
          "TRACK_MIX": "0017d6f0cffb229d4f9d5a1fc8e6bb"
        },
        "dateAdded": "2020-04-13T21:38:25.729+0000",
        "index": 50000,
        "itemUuid": "ac40d292-b7d5-44e9-bd5c-3e00f2223354"
      },
      "type": "track",
      "cut": null
    },
    {
      "item": {
        "id": 120433939,
        "title": "Eltsuhg Ibal Lasiti",
        "duration": 306,
        "replayGain": -8.36,
        "peak": 0.950745,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2019-11-01T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 7,
        "volumeNumber": 1,
        "version": null,
        "popularity": 1,
        "copyright": "Bereket Music Inc. (BMI) / Songs of Kobalt Music Publishing (BMI)",
        "description": null,
        "url": "http://www.tidal.com/track/120433939",
        "isrc": "US4GZ1804907",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3526620,
          "name": "The Daktaris",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3526620,
            "name": "The Daktaris",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 120433932,
          "title": "Soul Explosion",
          "cover": "dda87348-2ee8-4ab0-8f21-963616b09894",
          "videoCover": null,
          "releaseDate": "2018-12-07"
        },
        "mixes": {
          "TRACK_MIX": "0017172940171877b5c4a0d1537f59"
        },
        "dateAdded": "2020-04-10T09:06:08.554+0000",
        "index": 100000,
        "itemUuid": "8930c063-cc02-4965-88c5-4b80c971af86"
      },
      "type": "track",
      "cut": null
    }
  ]
}
```
