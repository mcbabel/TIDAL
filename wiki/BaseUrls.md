Tidal uses two different API BaseURLs:

* api.tidal.com/v1
* api.tidal.com/v2 (Feed and Activity API, Home Feed, Artist Page, My Collection Folders, Favorite Mixes, Search)

##### Update 2026-11
* tidal.com/v1 and tidal.com/v2: same-origin proxy of api.tidal.com/v1 and /v2 used by the web player since it moved from listen.tidal.com to tidal.com (listen.tidal.com redirects there). Same paths, parameters and headers.
* openapi.tidal.com/v2: the [Official TIDAL API](OfficialAPI) (JSON:API). The web player uses it in parallel to the private API (e.g. artists, playlists, save for later).
* resources.tidal.com/images/{id}/{width}x{height}.jpg: images. Replace the dashes of the image id (e.g. `cover`, `picture`, `squareImage`) with slashes: `cf203b3d-73e1-4239-98f6-49c231d8efcf` → `https://resources.tidal.com/images/cf203b3d/73e1/4239/98f6/49c231d8efcf/640x640.jpg`

Some v2 endpoints need the header ```x-tidal-client-version: {version}``` (web player: `2026.10.31`), otherwise they answer `400 Bad Request`.
