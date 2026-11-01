#### Example Request (verified 2026-11)
* Creates a playlist (v1). The apps now use [Create Playlist (My Collection)](my-collection-create-playlist).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/playlists?countryCode={country}```
##### Url-Encoded POST Parameter
```title: {title}```\
```description: {description}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```201 Created``` with the new playlist (format as [Get Playlist](playlist)) and an `ETag` header
