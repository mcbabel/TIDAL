#### Example Request (verified 2026-11)
* Replaces the item at `index` with another track.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items/{index}/replace?countryCode={country}```
##### Url-Encoded POST Parameter
```itemId: {track_id}```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}``` (Use eTag from the Get Playlist Header)\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```200 OK``` (empty body, new `ETag` header)
