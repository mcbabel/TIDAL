#### Example Request (verified 2026-11)
* Moves playlists into a folder.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/move?countryCode={country}```
##### Url Parameter
```folderId: {folderId}``` (`root` for the top level)\
```trns: trn:playlist:{uuid},trn:playlist:{uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

```204 No Content```
