#### Example Request (verified 2026-11)
* Creates a folder. The response is the new folder item (folder ids are UUIDs).
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/create-folder?countryCode={country}```
##### Url Parameter
```name: {title}```\
```folderId: root``` (parent folder)
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "trn": "trn:folder:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "itemType": "FOLDER",
  "addedAt": "2026-10-31T23:44:23.581+0000",
  "lastModifiedAt": "2026-10-31T23:44:23.581+0000",
  "name": "My Folder",
  "parent": null,
  "data": {
    "trn": "trn:folder:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    ...
  }
}
```
