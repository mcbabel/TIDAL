"My Collection" endpoints of the private v2 API used by the Android app (`com.aspiro.tidal` 2.215.0). They work like [My Collection Folders](my-collection-folders) (items with `trn`, `itemType`, `addedAt`, `lastModifiedAt`, `name`, `parent`, `data`; cursor pagination) but for albums, artists and mixes.

### Get Albums (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/albums/folders?folderId=root&limit={limit}&cursor={cursor}&order={enum}&orderDirection={enum}```
##### Common Url Parameter (added by the Android app)
```countryCode={country}```, ```locale={locale}```, ```deviceType=PHONE```, ```platform=ANDROID```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [
    {
      "trn": "trn:album:38519994",
      "itemType": "ALBUM",
      "addedAt": "2026-10-23T04:01:35.657+0000",
      "lastModifiedAt": "2026-10-23T04:01:35.657+0000",
      "name": "…",
      "parent": null,
      "data": { … }
    }
  ],
  "lastModifiedAt": "…",
  "totalNumberOfItems": 1,
  "cursor": null
}
```

### Get Artists (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/artists/folders?folderId=root&limit={limit}&cursor={cursor}&order={enum}&orderDirection={enum}&includeOnly={enum}```
##### Common Url Parameter (added by the Android app)
```countryCode={country}```, ```locale={locale}```, ```deviceType=PHONE```, ```platform=ANDROID```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [
    {
      "trn": "trn:artist:3529689",
      "itemType": "ARTIST",
      "addedAt": "2026-10-23T04:01:35.657+0000",
      "lastModifiedAt": "2026-10-23T04:01:35.657+0000",
      "name": "…",
      "parent": null,
      "data": { … }
    }
  ],
  "lastModifiedAt": "…",
  "totalNumberOfItems": 1,
  "cursor": null
}
```

### Get Mixes (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/mixes/folders?folderId=root&limit={limit}&cursor={cursor}&order={enum}&orderDirection={enum}&includeOnly={enum}```
##### Common Url Parameter (added by the Android app)
```countryCode={country}```, ```locale={locale}```, ```deviceType=PHONE```, ```platform=ANDROID```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [
    {
      "trn": "trn:mixe:0015fef37ea3cfb30058cef8a738ec",
      "itemType": "MIXE",
      "addedAt": "2026-10-23T04:01:35.657+0000",
      "lastModifiedAt": "2026-10-23T04:01:35.657+0000",
      "name": "…",
      "parent": null,
      "data": { … }
    }
  ],
  "lastModifiedAt": "…",
  "totalNumberOfItems": 1,
  "cursor": null
}
```

### Add Album (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/albums/add-favorite```
##### Url-Encoded PUT Parameter
```id: {albumId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "item": { "trn": "trn:album:38519994", "itemType": "ALBUM", "name": "Messier Objects", "parent": null, "data": { … }, … }
}
```

### Add Artist (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/artists/add-favorite```
##### Url-Encoded PUT Parameter
```artistId: {artistId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "item": { "trn": "trn:artist:11083", "itemType": "ARTIST", "name": "Kings Of Convenience", … }
}
```

### Add Mix (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/mixes/add-favorite```
##### Url-Encoded PUT Parameter
```id: {mixId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "item": { "trn": "trn:mix:0015fef37ea3cfb30058cef8a738ec", "itemType": "MIX", "name": "Object 3", … }
}
```

### Remove Albums / Artists / Mixes (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/{albums|artists|mixes}/remove```
##### Url-Encoded PUT Parameter
```trns: trn:album:{id}``` (or `trn:artist:{id}`, `trn:mix:{id}`, comma separated)
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```204 No Content```

### Create / Rename Artist Folder (answered 404 for the test account)
* Rename: `PUT …/my-collection/artists/rename` with `trn`, `name`, `returning`. Delete: `PUT …/my-collection/artists/remove` with `trns`.
* The test account got `404 {"error":"client_error","errorDescription":"bad_input"}`; artist folders seem not to be enabled for every account.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/artists/create-folder```
##### Url-Encoded PUT Parameter
```name: {name}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```

### Add Favorite Playlist (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/add-favorite```
##### Url-Encoded PUT Parameter
```uuid: {playlistUuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "item": { "trn": "trn:playlist:36ea71a8-445e-41a4-82ab-6628c581535d", "itemType": "PLAYLIST", "name": "Pop Hits", … }
}
```

### Get Playlists By Trn (verified 2026-11)
* Metadata only: `GET …/my-collection/playlists/folders/metadata?trns=…` (same response shape).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/items?trns={trn},{trn}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [ … ]
}
```

### Create Folder With Playlists (verified 2026-11)
* Like [Create Folder](my-collection-create-folder), with the playlists to move into the new folder.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/create-folder```
##### Url-Encoded PUT Parameter
```name: {name}```\
```folderId: root```\
```trns: trn:playlist:{uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "trn": "trn:folder:xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "itemType": "FOLDER",
  …
}
```

### Rename Playlist (verified 2026-11)
* Same endpoint as [Rename Folder](my-collection-rename-folder), with the playlist trn and an optional description.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/rename```
##### Url-Encoded PUT Parameter
```trn: trn:playlist:{uuid}```\
```name: {name}```\
```description: {description}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```204 No Content```

### Create Playlist (isPublic) (verified 2026-11)
* [Create Playlist](my-collection-create-playlist) with the visibility as Url parameter.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/folders/create-playlist?isPublic={true|false}```
##### Url-Encoded PUT Parameter
```name: {name}```\
```description: {description}```\
```folderId: root```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```

### Generate AI Playlist (answered 401 for the test account)
* The test account got `401 {"description":"AI playlist creation disabled","subStatus":1002}`. The official API offers the same feature as [playlistGenerations](official-ref-playlistGenerations) (verified there).
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/generate-playlist?name={prompt}&isPublic={true|false}```
##### Url-Encoded PUT Parameter
```folderId: root```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```

### Publish All Playlists Except (not executed)
* Makes all own playlists public except the ones in the body. Not executed: it would publish all private playlists of the test account.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/my-collection/playlists/set-public/all```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/json```
