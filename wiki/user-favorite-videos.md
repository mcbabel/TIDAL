#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/videos?countryCode={country}```
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
  "limit": 10,
  "offset": 0,
  "totalNumberOfItems": 1,
  "items": [
    {
      "created": "2020-10-15T21:22:38.365+0000",
      "item": {
        "id": 58782326,
        "title": "Branches Break",
        "volumeNumber": 1,
        "trackNumber": 1,
        "releaseDate": "2016-04-01T00:00:00.000+0000",
        "imagePath": null,
        "imageId": "280ef117-3f4d-43be-912f-3de0d3e8a4d9",
        "duration": 247,
        "quality": "MP4_1080P",
        "streamReady": true,
        "streamStartDate": "2018-02-05T00:00:00.000+0000",
        "allowStreaming": true,
        "explicit": false,
        "popularity": 3,
        "type": "Music Video",
        "adsUrl": null,
        "adsPrePaywallOnly": true,
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
        "album": null
      }
    }
  ]
}
```