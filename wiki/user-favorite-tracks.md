#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/tracks?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)\
```order={enum}```\
```orderDirection={enum}```
##### Order Enums
```DATE```\
```NAME```\
```ARTIST```\
```RELEASE_DATE```
##### OrderDirection Enums
```ASC```\
```DESC```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 14,
  "items": [
    {
      "created": "2020-07-07T20:59:26.297+0000",
      "item": {
        "id": 6757154,
        "title": "All Things",
        "duration": 366,
        "replayGain": -4.73,
        "peak": 0.985595,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2003-05-27T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 17,
        "volumeNumber": 1,
        "version": null,
        "popularity": 4,
        "copyright": "Ninja Tune",
        "url": "http://www.tidal.com/track/6757154",
        "isrc": "GBCFB0300096",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3521155,
          "name": "The Cinematic Orchestra",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3521155,
            "name": "The Cinematic Orchestra",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 6757137,
          "title": "Man With A Movie Camera",
          "cover": "0b27ba9b-d563-402e-8822-d53c28bf87b1",
          "videoCover": null
        },
        "mixes": {
          "TRACK_MIX": "0014c27ed8e95d8fb0d1b14c2eac24"
        }
      }
    },
    {
      "created": "2020-07-22T21:00:19.964+0000",
      "item": {
        "id": 6756308,
        "title": "At The End Of The Day",
        "duration": 192,
        "replayGain": -8.11,
        "peak": 0.999969,
        "allowStreaming": true,
        "streamReady": true,
        "streamStartDate": "2007-02-26T00:00:00.000+0000",
        "premiumStreamingOnly": false,
        "trackNumber": 12,
        "volumeNumber": 1,
        "version": null,
        "popularity": 8,
        "copyright": "Ninja Tune",
        "url": "http://www.tidal.com/track/6756308",
        "isrc": "GBCFB0601511",
        "editable": false,
        "explicit": false,
        "audioQuality": "LOSSLESS",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 3530358,
          "name": "Amon Tobin",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 3530358,
            "name": "Amon Tobin",
            "type": "MAIN"
          }
        ],
        "album": {
          "id": 6756296,
          "title": "Foley Room",
          "cover": "589d8cec-5470-4b84-bad0-96482217bfe5",
          "videoCover": null
        },
        "mixes": {
          "TRACK_MIX": "001ed4e867c220dac718522a2dc446"
        }
      }
    }
  ]
}
```
