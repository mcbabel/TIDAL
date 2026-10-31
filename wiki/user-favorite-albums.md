#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/albums?countryCode={country}```
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
  "totalNumberOfItems": 63,
  "items": [
    {
      "created": "2019-11-30T22:03:06.527+0000",
      "item": {
        "id": 68586854,
        "title": "10 Years Solo Live",
        "duration": 18322,
        "streamReady": true,
        "streamStartDate": "2015-11-20T00:00:00.000+0000",
        "allowStreaming": true,
        "premiumStreamingOnly": false,
        "numberOfTracks": 32,
        "numberOfVideos": 0,
        "numberOfVolumes": 4,
        "releaseDate": "2015-10-16",
        "copyright": "© 2015 Nonesuch Records Inc.",
        "type": "ALBUM",
        "version": null,
        "url": "http://www.tidal.com/album/68586854",
        "cover": "836ad968-446b-4b01-9ea4-10101c6bd5f3",
        "videoCover": null,
        "explicit": false,
        "upc": "075597947311",
        "popularity": 19,
        "audioQuality": "HI_RES",
        "audioModes": [
          "STEREO"
        ],
        "artist": {
          "id": 13979,
          "name": "Brad Mehldau",
          "type": "MAIN"
        },
        "artists": [
          {
            "id": 13979,
            "name": "Brad Mehldau",
            "type": "MAIN"
          }
        ]
      }
    },
    {
      "created": "2020-09-24T12:52:32.139+0000",
      "item": {
        "id": 84487164,
        "title": "A Humdrum Star (Deluxe)",
        "duration": 3505,
        "streamReady": true,
        "streamStartDate": "2018-02-09T00:00:00.000+0000",
        "allowStreaming": true,
        "premiumStreamingOnly": false,
        "numberOfTracks": 11,
        "numberOfVideos": 0,
        "numberOfVolumes": 1,
        "releaseDate": "2018-02-09",
        "copyright": "© 2018 Decca Records France",
        "type": "ALBUM",
        "version": "Deluxe",
        "url": "http://www.tidal.com/album/84487164",
        "cover": "e97c428e-21d1-43b4-a02a-cb0ce70e4826",
        "videoCover": null,
        "explicit": false,
        "upc": "00602567256311",
        "popularity": 21,
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
        ]
      }
    }
  ]
}
```
