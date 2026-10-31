Mapping of the private API (`api.tidal.com`) to the [Official TIDAL API](OfficialAPI) (`openapi.tidal.com/v2`). Third-party apps should prefer the official API where it covers the use case.

| Private API | Official API |
|---|---|
| [```GET tracks/{id}```](track) | [```GET /tracks/{id}```](official-track) |
| ```GET tracks?ids=...``` / ISRC lookup | ```GET /tracks?filter[id]=...``` / ```GET /tracks?filter[isrc]=...``` |
| [```GET albums/{id}```](album) | ```GET /albums/{id}``` |
| [```GET albums/{id}/items```](album-items) | ```GET /albums/{id}/relationships/items``` |
| [```GET artists/{id}```](artist) | ```GET /artists/{id}``` |
| [```GET artists/{id}/albums```](artist-albums) | ```GET /artists/{id}/relationships/albums``` |
| [```GET artists/{id}/toptracks```](artist-toptracks) | ```GET /artists/{id}/relationships/tracks``` |
| [```GET artists/{id}/videos```](artist-videos) | ```GET /artists/{id}/relationships/videos``` |
| [```GET artists/{id}/similar```](artist-similar) | ```GET /artists/{id}/relationships/similarArtists``` |
| [```GET artists/{id}/radio```](artist-radio) / [mix](artist-mix) | ```GET /artists/{id}/relationships/radio``` |
| [```GET artists/{id}/bio```](artist-bio) | ```GET /artists/{id}/relationships/biography``` |
| [```GET tracks/{id}/radio```](track-radio) / [mix](track-mix) | ```GET /tracks/{id}/relationships/radio``` |
| [```GET tracks/{id}/recommendations```](track-recommendations) | ```GET /tracks/{id}/relationships/similarTracks``` |
| [```GET videos/{id}```](video) | ```GET /videos/{id}``` |
| [```GET playlists/{uuid}```](playlist) | ```GET /playlists/{id}``` |
| [```GET playlists/{uuid}/items```](playlist-items) | ```GET /playlists/{id}/relationships/items``` |
| [```POST playlists/{uuid}/items```](playlist-add-item) | [```POST /playlists/{id}/relationships/items```](official-playlists) |
| [```POST playlists/{uuid}/items/{index}```](playlist-move-item) | [```PATCH /playlists/{id}/relationships/items```](official-playlists) (by `itemId`, not index) |
| [```DELETE playlists/{uuid}/items/{index}```](playlist-delete-item) | [```DELETE /playlists/{id}/relationships/items```](official-playlists) |
| [```POST playlists/{uuid}```](playlist-rename) / [set-public](playlist-set-public) | [```PATCH /playlists/{id}```](official-playlists) |
| [```DELETE playlists/{uuid}```](playlist-delete) | ```DELETE /playlists/{id}``` |
| [```PUT my-collection/.../create-playlist```](my-collection-create-playlist) | [```POST /playlists```](official-playlists) |
| [```GET users/{id}/playlists```](user-playlists) | ```GET /playlists?filter[owners.id]=me``` |
| [```GET search```](search) / [v2 search](search-v2) | [```GET /searchResults?filter[query]=...```](official-searchResults) |
| [```GET users/{id}/favorites/tracks```](user-favorite-tracks) | [```GET /userCollectionTracks/me/relationships/items```](official-userCollections) |
| [```POST users/{id}/favorites/tracks```](user-add-favorite-track) | [```POST /userCollectionTracks/me/relationships/items```](official-userCollections) |
| [```DELETE users/{id}/favorites/tracks/{id}```](user-delete-favorite-track) | [```DELETE /userCollectionTracks/me/relationships/items```](official-userCollections) |
| albums / artists / videos / playlists favorites | ```/userCollectionAlbums```, ```/userCollectionArtists```, ```/userCollectionVideos```, ```/userCollectionPlaylists``` |
| [```GET pages/my_collection_my_mixes```](page-mymixes) | ```GET /userDailyMixes/me```, ```/userDiscoveryMixes/me```, ```/userNewReleaseMixes/me``` |
| [```GET users/{id}```](user) / [sessions](sessions) | [```GET /users/me```](official-users) |
| [```GET tracks/{id}/playbackinfo```](track-playbackinfo) | [```GET /trackManifests/{id}```](official-trackManifests) |
| [```GET videos/{id}/playbackinfopostpaywall```](video-playbackinfopostpaywall) | ```GET /videoManifests/{id}``` |
| Image ids (`cover`, `picture`) + resources.tidal.com | ```coverArt``` / ```profileArt``` relationships (`artworks` with `files[].href`) |

##### Not available for third-party apps (yet)
Pages (home, explore, genres, moods), activity feed, lyrics, credits, user profiles, playlist folders, mixes favorites, play queue, offline. These endpoints exist in the official spec but are marked `INTERNAL`.

##### Differences to keep in mind
* Ids are strings. Durations are ISO 8601 (`PT2M4S`) instead of seconds. Popularity is `0.0` - `1.0` instead of `0` - `100`.
* Pagination is cursor based (`links.next`) instead of `limit`/`offset`.
* Related data must be requested with `include=...`.
* Playlist entries are addressed by `meta.itemId` instead of the index, no ETag needed.
