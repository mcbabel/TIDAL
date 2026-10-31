#### Example Request (verified 2026-11)
* Playlists created by the user. Item format as [Get Playlist](playlist).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/playlists?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 25,
  "items": [
    {
      "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "title": "...",
      "numberOfTracks": 0,
      "numberOfVideos": 0,
      "creator": {
        "id": 123456789
      },
      "description": "",
      "duration": 0,
      "lastUpdated": "2026-01-01T00:00:00.000+0000",
      "created": "2026-01-01T00:00:00.000+0000",
      "type": "USER",
      "publicPlaylist": false,
      "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "popularity": 0,
      "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "customImageUrl": null,
      "promotedArtists": [],
      "lastItemAddedAt": "2026-01-01T00:00:00.000+0000"
    }
  ]
}
```
