#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/clients/{clientId}/offline/playlists?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 1,
  "totalNumberOfItems": 7,
  "items": [
    {
      "created": "2020-07-09T10:57:25.288+0000",
      "item": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "Su-Bo's Meltdown",
        "numberOfTracks": 83,
        "numberOfVideos": 0,
        "creator": {
          "id": xxxxxxxxx
        },
        "description": "",
        "duration": 28502,
        "lastUpdated": "2020-09-10T14:20:08.867+0000",
        "created": "2020-07-07T21:10:25.507+0000",
        "type": "USER",
        "publicPlaylist": false,
        "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "popularity": 0,
        "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "promotedArtists": [
        ],
        "lastItemAddedAt": "2020-08-24T18:42:25.334+0000"
      }
    }
  ]
}
```

#### Update 2026-11 (verified)
Still exists. With a `clientId` that is not authorized for offline it answers `400 {"subStatus":1002,"userMessage":"Bad request"}`. Offline-authorized clients are only the mobile/desktop apps (see [Get User Clients](user-clients), `authorizedForOffline`).
