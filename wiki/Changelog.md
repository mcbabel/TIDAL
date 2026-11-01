#### 11-01-2026 (complete coverage)
Coverage check against the JavaScript of the web player (all API calls extracted) and the full official OpenAPI spec. See [Status of legacy endpoints](legacy-status) for the method and the remaining limits.

Private API:
  - Created Entries: User Blocks, User Activity, User Onboarding & Early Access, Welcome / Artist Picker, Contributor Page, Artist Playable, Artist View All (v2), Home Feed By Vibe / View All, Search Suggestions, Image Metadata, My Collection Artists (v2), Purchases & Marketplace, Onboarding (v2), Music Assistant (AI Chat), DRM (Widevine / FairPlay), Streaming Privileges (rt/connect + WebSocket), Cloud Queue (TIDAL Connect), Web Session, Event Batch, Replace Playlist Item, Create Playlist (v1)
  - Updated: Track PlaybackInfo (headers `x-tidal-streamingsessionid`, `x-tidal-prefetch`, error subStatus codes)
  - Created Page: [Status of legacy endpoints](legacy-status). All former "not yet documented" entries are resolved or explained.

Official API:
  - Created Entries: reference pages for all 89 resources with all 438 operations (parameters, request bodies, attributes, relationships, access tier, scopes), generated from the spec
  - Updated: [List of all Endpoints](official-endpoints) now lists all 438 operations

#### 11-01-2026
Documentation updated to the current state of the TIDAL API. All endpoints marked **(verified 2026-11)** were called against the live API (web player version 2026.10.31, official API spec 1.10.218). Write endpoints were tested with temporary test objects that were deleted afterwards.

General:
  - Created Pages: [Audio Quality](AudioQuality) (MQA removed, `HI_RES_LOSSLESS`), [Official TIDAL API](OfficialAPI), [Migration Guide](Migration), [Changelog](Changelog)
  - Updated: [BaseUrls](BaseUrls) (tidal.com proxy, openapi.tidal.com, resources.tidal.com), [AuthUrls](AuthUrls), [Deprecation](Deprecation)

Authentication:
  - Updated: [Authentication](Authentication) (PKCE, Client Credentials, anonymous access, refresh token rotation, scopes), [Post oAuth Token](auth-token) (client_credentials, update_client), [Post oAuth Device Authorization](auth-device_authorization) (`app_approval`)
  - Created Entries: [Authorization Code + PKCE](auth-pkce), [Client Credentials](auth-client-credentials), [Get Session](sessions)

Playback:
  - Created Entry: [Get Track PlaybackInfo](track-playbackinfo)
  - Updated: PlaybackInfoPostPaywall, PlaybackInfoPrePaywall, StreamUrl (tracks: deprecated), Video PlaybackInfoPostPaywall, Video StreamUrl

Catalog:
  - Updated (new fields): Track, Album, Artist, Video, Playlist, Search, Artist Links, Mix Items
  - Created Entries: Artist Similar, Artist Radio, Artist Page v2, Album Tracks, Album Similar, Track Credits, Track Radio, Track Recommendations, Track Lyrics, Genres, Country, Search v2
  - Created Entries: Page Mix, Page Artist, Page Album, Page For You, Page HiRes, Page Genre, Page Moods, Home Feed (v2)

User:
  - Created Entries: Add User Favorite Album / Artist / Playlist / Track / Video (linked in the sidebar before, but missing), Get User Playlists, Get User Public Playlists, Get User Profile
  - Created Entries: My Collection Folders (get, create playlist, create folder, rename, move, remove), Set Playlist Public / Private
  - Updated: User, User Subscription, Favorite Mixes (cursor pagination), Delete Favorites, Playlist Add / Move / Delete Item, Rename / Delete Playlist, Feed Activities, Feed Unseen

Official API:
  - Created Entries: [List of all Endpoints](official-endpoints) (generated from the spec), [Get Track](official-track), [Search](official-searchResults), [Get TrackManifest](official-trackManifests), [Playlists](official-playlists), [User Collections](official-userCollections), [Get User](official-users)

Fixes:
  - Endpoints: filled empty links, fixed `page-mymix` → `page-mymixes`, `POST playlists/{uuid}/items/{indices}` → Move Playlist Item

#### 12-25-2020
  - Created Entries: Get Favorite Mixes, Add Favorite Mixes, Delete Favorite Mixes (Thank you @AustinJ235)

#### 11-14-2020
  - Created Entry: Activity Feed
  - Created Entry: Second API
  - Created Entry: Logout Endpoint
