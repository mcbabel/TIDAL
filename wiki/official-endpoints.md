Generated from the official OpenAPI spec version `1.10.218` (2026-11-01): https://tidal-music.github.io/tidal-api-reference/tidal-api-oas.json

The spec contains 438 operations: 101 are open to third-party apps (listed here), 336 are internal to TIDAL and 1 partner-only.

Base url: ```https://openapi.tidal.com/v2```

Detailed pages: [Get Track](official-track), [Search](official-searchResults), [TrackManifests](official-trackManifests), [Playlists](official-playlists), [User Collections](official-userCollections), [User](official-users)

###### albums
```GET /albums``` Get multiple albums. Auth: Client Credentials, PKCE

```GET /albums/{id}``` Get single album. Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/artists``` Get artists relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/coverArt``` Get coverArt relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/items``` Get items relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/providers``` Get providers relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/similarAlbums``` Get similarAlbums relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /albums/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). Auth: Client Credentials, PKCE

###### artistRoles
```GET /artistRoles/{id}``` Get single artistRole. Auth: Client Credentials, PKCE

###### artists
```GET /artists``` Get multiple artists. Auth: Client Credentials, PKCE

```GET /artists/{id}``` Get single artist. Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/albums``` Get albums relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/biography``` Get biography relationship ("to-one"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/profileArt``` Get profileArt relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/radio``` Get radio relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/roles``` Get roles relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/similarArtists``` Get similarArtists relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/trackProviders``` Get trackProviders relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/tracks``` Get tracks relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /artists/{id}/relationships/videos``` Get videos relationship ("to-many"). Auth: Client Credentials, PKCE

###### artworks
```GET /artworks``` Get multiple artworks. Auth: Client Credentials, PKCE

```GET /artworks/{id}``` Get single artwork. Auth: Client Credentials, PKCE

```GET /artworks/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: Client Credentials, PKCE

###### playlists
```GET /playlists``` Get multiple playlists. Auth: Client Credentials, PKCE (scopes: playlists.read)

[```POST /playlists```][+](official-playlists) Create single playlist. Auth: PKCE (user) (scopes: playlists.write)

```DELETE /playlists/{id}``` Delete single playlist. Auth: PKCE (user) (scopes: playlists.write)

```GET /playlists/{id}``` Get single playlist. Auth: Client Credentials, PKCE

```PATCH /playlists/{id}``` Update single playlist. Auth: PKCE (user) (scopes: playlists.write)

```GET /playlists/{id}/relationships/collaboratorProfiles``` Get collaboratorProfiles relationship ("to-many"). Auth: Client Credentials, PKCE **Deprecated**

```GET /playlists/{id}/relationships/collaborators``` Get collaborators relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /playlists/{id}/relationships/coverArt``` Get coverArt relationship ("to-many"). Auth: Client Credentials, PKCE

```DELETE /playlists/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: playlists.write)

```GET /playlists/{id}/relationships/items``` Get items relationship ("to-many"). Auth: Client Credentials, PKCE

```PATCH /playlists/{id}/relationships/items``` Update items relationship ("to-many"). Auth: PKCE (user) (scopes: playlists.write)

[```POST /playlists/{id}/relationships/items```][+](official-playlists) Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: playlists.write)

```GET /playlists/{id}/relationships/ownerProfiles``` Get ownerProfiles relationship ("to-many"). Auth: Client Credentials, PKCE **Deprecated**

```GET /playlists/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: Client Credentials, PKCE

###### providers
```GET /providers/{id}``` Get single provider. Auth: Client Credentials, PKCE

###### searchResults
[```GET /searchResults```][+](official-searchResults) Get search results by query. Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/albums``` Get albums relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/artists``` Get artists relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/playlists``` Get playlists relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/topHits``` Get topHits relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/tracks``` Get tracks relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchResults/{id}/relationships/videos``` Get videos relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

###### searchSuggestions
```GET /searchSuggestions``` Get search suggestions by query. Auth: Client Credentials, PKCE (scopes: search.read)

```GET /searchSuggestions/{id}/relationships/directHits``` Get directHits relationship ("to-many"). Auth: Client Credentials, PKCE (scopes: search.read)

###### trackManifests
[```GET /trackManifests/{id}```][+](official-trackManifests) Get single trackManifest. Auth: Client Credentials, PKCE (scopes: playback)

###### tracks
```GET /tracks``` Get multiple tracks. Auth: Client Credentials, PKCE

[```GET /tracks/{id}```][+](official-track) Get single track. Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/albums``` Get albums relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/artists``` Get artists relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/providers``` Get providers relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/radio``` Get radio relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/similarTracks``` Get similarTracks relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/sourceFile``` Get sourceFile relationship ("to-one"). Auth: Client Credentials, PKCE

```GET /tracks/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). Auth: Client Credentials, PKCE

###### usageRules
```GET /usageRules/{id}``` Get single usageRule. Auth: Client Credentials, PKCE

###### userCollectionAlbums
```GET /userCollectionAlbums/{id}``` Get single userCollectionAlbum. Auth: PKCE (user) (scopes: collection.read)

```DELETE /userCollectionAlbums/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionAlbums/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

```POST /userCollectionAlbums/{id}/relationships/items``` Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionAlbums/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

###### userCollectionArtists
```GET /userCollectionArtists/{id}``` Get single userCollectionArtist. Auth: PKCE (user) (scopes: collection.read)

```DELETE /userCollectionArtists/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionArtists/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

```POST /userCollectionArtists/{id}/relationships/items``` Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionArtists/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

###### userCollectionPlaylists
```GET /userCollectionPlaylists/{id}``` Get single userCollectionPlaylist. Auth: PKCE (user) (scopes: collection.read)

```DELETE /userCollectionPlaylists/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionPlaylists/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

```POST /userCollectionPlaylists/{id}/relationships/items``` Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionPlaylists/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

###### userCollectionTracks
```GET /userCollectionTracks/{id}``` Get single userCollectionTrack. Auth: PKCE (user) (scopes: collection.read)

```DELETE /userCollectionTracks/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

[```GET /userCollectionTracks/{id}/relationships/items```][+](official-userCollections) Get items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

[```POST /userCollectionTracks/{id}/relationships/items```][+](official-userCollections) Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionTracks/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

###### userCollectionVideos
```GET /userCollectionVideos/{id}``` Get single userCollectionVideo. Auth: PKCE (user) (scopes: collection.read)

```DELETE /userCollectionVideos/{id}/relationships/items``` Delete from items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionVideos/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

```POST /userCollectionVideos/{id}/relationships/items``` Add to items relationship ("to-many"). Auth: PKCE (user) (scopes: collection.write)

```GET /userCollectionVideos/{id}/relationships/owners``` Get owners relationship ("to-many"). Auth: PKCE (user) (scopes: collection.read)

###### userDailyMixes
```GET /userDailyMixes/{id}``` Get single userDailyMixe. Auth: PKCE (user) (scopes: recommendations.read)

```GET /userDailyMixes/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: recommendations.read)

###### userDiscoveryMixes
```GET /userDiscoveryMixes/{id}``` Get single userDiscoveryMixe. Auth: PKCE (user) (scopes: recommendations.read)

```GET /userDiscoveryMixes/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: recommendations.read)

###### userNewReleaseMixes
```GET /userNewReleaseMixes/{id}``` Get single userNewReleaseMixe. Auth: PKCE (user) (scopes: recommendations.read)

```GET /userNewReleaseMixes/{id}/relationships/items``` Get items relationship ("to-many"). Auth: PKCE (user) (scopes: recommendations.read)

###### users
[```GET /users/{id}```][+](official-users) Get single user. Auth: PKCE (user) (scopes: user.read)

###### videoManifests
```GET /videoManifests/{id}``` Get single videoManifest. Auth: Client Credentials, PKCE (scopes: playback)

###### videos
```GET /videos``` Get multiple videos. Auth: Client Credentials, PKCE

```GET /videos/{id}``` Get single video. Auth: Client Credentials, PKCE

```GET /videos/{id}/relationships/albums``` Get albums relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /videos/{id}/relationships/artists``` Get artists relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /videos/{id}/relationships/providers``` Get providers relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /videos/{id}/relationships/thumbnailArt``` Get thumbnailArt relationship ("to-many"). Auth: Client Credentials, PKCE

```GET /videos/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). Auth: Client Credentials, PKCE
