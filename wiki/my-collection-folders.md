#### Example Request (verified 2026-11)
* Playlists (own + favorite) and folders of the user, as shown in "My Collection". Max `limit` is 50.
* Pagination is cursor based: pass `cursor={cursor}` from the previous response. `offset` is ignored.
* `folderId=root` for the top level, otherwise the folder id.
* All items without folder structure: `GET https://api.tidal.com/v2/my-collection/playlists/folders/flattened?includeOnly={enum}&...` (the web player uses `includeOnly=FAVORITE_PLAYLIST`, and sends `If-None-Match`).
* Items are identified by a TIDAL resource name: `trn:playlist:{uuid}` or `trn:folder:{id}`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders?folderId={folderId}&includeOnly={enum}&offset=0&limit=50&order={enum}&orderDirection={enum}&countryCode={country}&locale={locale}&deviceType={enum}```
##### includeOnly Enums
``` ``` (empty: everything)\
```PLAYLIST```\
```FOLDER```\
```FAVORITE_PLAYLIST```
##### Order Enums
```DATE```\
```NAME```
##### OrderDirection Enums
```ASC```\
```DESC```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "lastModifiedAt": "2026-10-30T23:57:36.717+0000",
  "items": [
    {
      "trn": "trn:playlist:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "itemType": "PLAYLIST",
      "addedAt": "2026-10-01T10:40:48.432+0000",
      "lastModifiedAt": "2026-10-30T23:57:36.716+0000",
      "name": "My Playlist",
      "parent": null,
      "data": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "type": "USER",
        "creator": {
          "id": 123456789,
          "name": null,
          "picture": null,
          "type": "USER"
        },
        "curators": [ ... ],
        "contentBehavior": "UNRESTRICTED",
        "sharingLevel": "PRIVATE",
        "status": "READY",
        "source": "DEFAULT",
        "title": "My Playlist",
        "description": "",
        "image": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "squareImage": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "customImageUrl": null,
        "url": "http://www.tidal.com/playlist/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "created": "...",
        "lastUpdated": "...",
        "lastItemAddedAt": "...",
        "duration": 0,
        "numberOfTracks": 284,
        "numberOfVideos": 0,
        "promotedArtists": [ ... ],
        "trn": "trn:playlist:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "itemType": "PLAYLIST"
      }
    }
  ],
  "totalNumberOfItems": 32,
  "cursor": null
}
```
