#### Example Request
* To prevent corruption you need to extract the eTag Value from the Get Playlist Header
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items/{indices}?countryCode={country}```
##### Url-Encoded POST Parameter
```toIndex: {index}```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}``` (Use eTag from the Get Playlist Header)

#### Update 2026-11 (verified)
Still works. Response: `200 OK` with empty body.
