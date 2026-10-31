#### Example Request
* To prevent corruption you need to extract the eTag Value from the Get Playlist Header
##### Method
```DELETE```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items/{indices}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}``` (Use eTag from the Get Playlist Header)

#### Example Response
```HTTP 200 No Error```

#### Update 2026-11 (verified)
Still works. Optional Url Parameter `order=INDEX&orderDirection=ASC` (sent by python-tidal).
