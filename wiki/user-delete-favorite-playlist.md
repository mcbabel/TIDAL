#### Example Request
##### Method
```DELETE```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/playlists/{uuid}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

```
204 No Content
````

#### Update 2026-11 (verified)
Still works: `200 OK` with empty body (tested with a playlist that was added via [add-favorites](user-add-favorite-playlist) before).
