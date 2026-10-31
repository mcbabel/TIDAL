#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/playlists?countryCode={country}```
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
      "created": "2020-04-03T13:52:50.116+0000",
      "item": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "<3333",
        "numberOfTracks": 16,
        "numberOfVideos": 0,
        "creator": {
          "id": xxxxxxxx
        },
        "description": "",
        "duration": 4141,
        "lastUpdated": "2020-04-26T19:51:14.842+0000",
        "created": "2019-03-24T11:08:49.091+0000",
        "type": "USER",
        "publicPlaylist": false,
        "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "popularity": 0,
        "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "promotedArtists": [
        ],
        "lastItemAddedAt": null
      }
    }
  ]
}
```