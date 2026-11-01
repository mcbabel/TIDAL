#### Example Request (verified 2026-11)
* Content of a genre (verified): `GET genres/{path}/{playlists|artists|albums|tracks|videos}?countryCode={country}`. `path` from this list, e.g. `Pop`. Unknown paths answer `404 "Category not found"`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/genres?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
[
  {
    "name": "Deutsch",
    "path": "Local",
    "hasPlaylists": true,
    "hasArtists": false,
    "hasAlbums": true,
    "hasTracks": true,
    "hasVideos": true,
    "image": "7b24b83d-ea84-49e8-9ba2-9473dad9cd75"
  }
]
```
