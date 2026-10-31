#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/playlistsAndFavoritePlaylists?countryCode={country}```
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
  "totalNumberOfItems": 12,
  "items": [
    {
      "type": "USER_CREATED",
      "created": "2019-11-24T18:30:09.790+0000",
      "playlist": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "Jazz",
        "numberOfTracks": 6,
        "numberOfVideos": 0,
        "creator": {
          "id": xxxxxxxx
        },
        "description": "",
        "duration": 3137,
        "lastUpdated": "2020-03-28T18:23:07.299+0000",
        "created": "2019-11-24T18:30:09.790+0000",
        "type": "USER",
        "publicPlaylist": false,
        "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "popularity": 0,
        "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "promotedArtists": [
        ],
        "lastItemAddedAt": "2020-03-28T18:23:06.586+0000"
      }
    },
    {
      "type": "USER_CREATED",
      "created": "2019-12-24T10:30:05.218+0000",
      "playlist": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "Lounge",
        "numberOfTracks": 16,
        "numberOfVideos": 0,
        "creator": {
          "id": xxxxxxxxx
        },
        "description": "",
        "duration": 5244,
        "lastUpdated": "2020-10-04T16:27:14.753+0000",
        "created": "2019-12-24T10:30:05.218+0000",
        "type": "USER",
        "publicPlaylist": false,
        "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "popularity": 0,
        "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "promotedArtists": [
        ],
        "lastItemAddedAt": "2020-07-10T16:46:43.165+0000"
      }
    }
  ]
}
```
