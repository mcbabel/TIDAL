#### Example Request (verified 2026-11)
* Playlists are added via the v2 My Collection endpoint (the apps put favorite playlists into folders).
* Adding more than one playlist is possible by separating the uuids: ```{uuid},{uuid}```
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/add-favorites?folderId={folderId}&uuids={uuid}&countryCode={country}```
##### Url Parameter
```folderId: root``` (or the id of a folder)\
```uuids: {uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "addedItems": [
    {
      "trn": "trn:playlist:36ea71a8-445e-41a4-82ab-6628c581535d",
      "itemType": "PLAYLIST",
      "addedAt": "2026-11-01T00:14:33.582+0000",
      "lastModifiedAt": "2026-10-30T04:12:21.082+0000",
      ...
    }
  ]
}
```
