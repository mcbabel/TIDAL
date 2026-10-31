#### Example Request
* Playlists are added via the v2 My Collection endpoint (the apps put favorite playlists into folders).
* Adding more than one playlist is possible by separating the uuids: ```{uuid},{uuid}```
* Source: python-tidal (EbbLabs). Not live-verified (write endpoint).
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
