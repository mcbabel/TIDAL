#### Example Request
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}?countryCode={country}```
##### Url-Encoded POST Parameter
```title: {title}```\
```description: {description}```
##### Header
```authorization: Bearer {access_token}```

#### Update 2026-11 (verified)
Still works. Response: `200 OK` with empty body. Send ```If-None-Match: {eTag}``` (from the Get Playlist Header) like for the item endpoints.
Visibility: [Set Playlist Public](playlist-set-public) / [Set Playlist Private](playlist-set-private).
