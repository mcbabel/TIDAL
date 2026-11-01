### Get Playlist Status (verified 2026-11)
* Polled by the app after creating or changing a playlist.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/playlists/{uuid}/status```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "status": "READY"
}
```

### Get Enriched Playlist (verified 2026-11)
* Playlist with follow info and creator profile; `404 "Playlist not found"` for private playlists.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/user-playlists/{uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "playlist": { … },
  "followInfo": { "nrOfFollowers": 0, "followed": false, "tidalResourceName": "trn:playlist:…", "followType": "PLAYLIST" },
  "profile": { … }
}
```

### Set Playlists Public (bulk) (verified 2026-11)
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/playlists/set-public```
##### Url-Encoded PUT Parameter
```playlistUuids: {uuid},{uuid}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
```200 OK``` (empty body)

### Set / Remove Playlist Image (answered 404 bad_input)
* Remove: `PUT v2/playlists/{uuid}/images/remove?userId={userId}`.
* Needs an image uploaded before; with a non-existent image id (add) and on a playlist without image (remove) both answered `404 {"errorDescription":"bad_input"}`.
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/playlists/{uuid}/images/add?imageId={imageId}&userId={userId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```

### Copy Items From Another Playlist (verified 2026-11)
* Variant of [Add Playlist Item](playlist-add-item) used by the app.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}/items```
##### Url-Encoded POST Parameter
```fromPlaylistUuid: {uuid}```\
```onArtifactNotFound: SKIP```\
```onDupes: SKIP```
##### Header
```authorization: Bearer {access_token}```\
```If-None-Match: {eTag}```\
```Content-Type: application/x-www-form-urlencoded```
#### Example Response
``` yaml
{
  "lastUpdated": 1793498130125,
  "addedItemIds": [ 570268437, 556252691, … ]
}
```
