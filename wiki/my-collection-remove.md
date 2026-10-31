#### Example Request (verified 2026-11)
* Removes folders or (favorite) playlists from My Collection.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/remove?countryCode={country}```
##### Url Parameter
```trns: trn:folder:{id},trn:playlist:{uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

```204 No Content```
