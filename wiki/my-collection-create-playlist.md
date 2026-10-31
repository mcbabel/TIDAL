#### Example Request (verified 2026-11)
* Creates a playlist inside a folder. The response is the new folder item, the playlist itself is in `data` (with `uuid`).
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/create-playlist?countryCode={country}```
##### Url Parameter
```name: {title}```\
```description: {description}```\
```folderId: root``` (or a folder id)
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "trn": "trn:playlist:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "itemType": "PLAYLIST",
  "addedAt": "2026-10-31T23:44:25.756+0000",
  "lastModifiedAt": "2026-10-31T23:44:25.731+0000",
  "name": "My Playlist",
  "parent": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "My Folder",
    ...
  },
  "data": {
    "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "type": "USER",
    "title": "My Playlist",
    "description": "",
    ...
  }
}
```
