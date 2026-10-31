"My Collection" (favorites) of the Official API. One resource per type, the user id `me` refers to the logged-in user.

| Type | Path |
|---|---|
| Tracks | `/userCollectionTracks/me/relationships/items` |
| Albums | `/userCollectionAlbums/me/relationships/items` |
| Artists | `/userCollectionArtists/me/relationships/items` |
| Videos | `/userCollectionVideos/me/relationships/items` |
| Playlists | `/userCollectionPlaylists/me/relationships/items` |

Older versions of the API had a single `/userCollections/{id}` resource. It was split into these per-type resources.

### Get Items (verified 2026-11)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionTracks/me/relationships/items?sort=-addedAt&include=items```
##### sort Enums
```addedAt```, ```albums.title```, ```artists.name```, ```duration```, ```title``` (prefix `-` for descending)
##### Header
```Authorization: Bearer {access_token}``` (PKCE, scope `collection.read`)\
```Accept: application/vnd.api+json```
#### Example Response
``` yaml
{
  "data": [
    {
      "id": "511678925",
      "type": "tracks",
      "meta": {
        "addedAt": "2026-10-20T14:35:03.543Z"
      }
    },
    ...
  ],
  "links": {
    "self": "/userCollectionTracks/me/relationships/items?sort=-addedAt",
    "next": "/userCollectionTracks/me/relationships/items?sort=-addedAt&page%5Bcursor%5D=xxxxxx",
    "meta": {
      "nextCursor": "xxxxxx"
    }
  }
}
```

### Add Items (verified 2026-11)
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userCollectionTracks/me/relationships/items```
##### Header
```Authorization: Bearer {access_token}``` (PKCE, scope `collection.write`)\
```Content-Type: application/vnd.api+json```
##### Body
``` yaml
{
  "data": [
    { "type": "tracks", "id": "38519997" }
  ]
}
```
#### Example Response
``` yaml
{
  "data": [
    {
      "id": "38519997",
      "type": "tracks",
      "meta": {
        "addedAt": "2026-10-31T23:45:07.932Z"
      }
    }
  ],
  "links": {
    "self": "/userCollectionTracks/me/relationships/items"
  },
  "meta": {
    "skipped": []
  }
}
```

### Remove Items (verified 2026-11)
```DELETE https://openapi.tidal.com/v2/userCollectionTracks/me/relationships/items``` with the same body as Add Items → `200 OK` `{"links": {...}, "meta": {}}`

### Mixes
```GET https://openapi.tidal.com/v2/userDailyMixes/me?include=items``` (also `userDiscoveryMixes`, `userNewReleaseMixes`), scope `recommendations.read`. The mixes are returned as `playlists` resources in the `items` relationship (verified 2026-11).
