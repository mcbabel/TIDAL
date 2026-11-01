###### Artists

[```GET artists/{id}```][+](artist)

[```GET artists/{id}/bio```][+](artist-bio)

[```GET artists/{id}/links```][+](artist-links)

[```GET artists/{id}/mix```][+](artist-mix)

[```GET artists/{id}/toptracks```][+](artist-toptracks)

[```GET artists/{id}/videos```][+](artist-videos)

[```GET artists/{id}/albums```][+](artist-albums)

[```GET artists/{id}/similar```][+](artist-similar)

[```GET artists/{id}/radio```][+](artist-radio)

[```GET v2/artist/{id}```][+](artist-page-v2)

[```GET v2/artist/@{handle}```][+](artist-page-v2)

[```GET v2/artist/{id}/playable```][+](artist-playable)

[```GET v2/artist/{sourceType}/view-all```][+](artist-view-all)

[```GET pages/contributor```][+](page-contributor)
###### Albums

[```GET albums/{id}```][+](album)

[```GET albums/{id}/credits```][+](album-credits)

[```GET albums/{id}/items```][+](album-items)

[```GET albums/{id}/items/credits```][+](album-items-credits)

[```GET albums/{id}/review```][+](album-review)

[```GET albums/{id}/tracks```][+](album-tracks)

[```GET albums/{id}/similar```][+](album-similar)
###### Playlists

[```POST playlists/{uuid}/items```][+](playlist-add-item)

[```DELETE playlists/{uuid}```][+](playlist-delete)

[```DELETE playlists/{uuid}/items/{indices}```][+](playlist-delete-item)

[```GET playlists/{uuid}```][+](playlist)

[```GET playlists/{uuid}/items```][+](playlist-items)

[```GET playlists/{uuid}/recommendations/items```][+](playlist-recommendations-items)

[```POST playlists/{uuid}/items/{indices}```][+](playlist-move-item)

[```POST playlists/{uuid}/items/{index}/replace```][+](playlist-replace-item)

[```POST playlists/{uuid}```][+](playlist-rename)

[```PUT v2/playlists/{uuid}/set-public```][+](playlist-set-public)

[```PUT v2/playlists/{uuid}/set-private```][+](playlist-set-private)
###### Tracks

[```GET tracks/{id}/contributors```][+](track-contributors)

[```GET tracks/{id}/mix```][+](track-mix)

[```GET tracks/{id}/streamUrl```][+](track-streamUrl)

[```GET tracks/{id}/playbackinfopostpaywall```][+](track-playbackinfopostpaywall)

[```GET tracks/{id}/playbackinfoprepaywall```][+](track-playbackinfoprepaywall)

[```GET tracks/{id}```][+](track)

[```GET tracks/{id}/playbackinfo```][+](track-playbackinfo)

[```GET tracks/{id}/credits```][+](track-credits)

[```GET tracks/{id}/radio```][+](track-radio)

[```GET tracks/{id}/recommendations```][+](track-recommendations)

[```GET tracks/{id}/lyrics```][+](track-lyrics)
###### Videos

[```GET videos/{id}/contributors```][+](video-contributors)

[```GET videos/{id}/streamUrl```][+](video-streamUrl)

[```GET videos/{id}/playbackinfopostpaywall```][+](video-playbackinfopostpaywall)

[```GET videos/{id}/playbackinfoprepaywall```][+](video-playbackinfoprepaywall)

[```GET videos/{id}```][+](video)
###### Mixes

[```GET mixes/{mixId}/items```][+](mix-items)
###### User
[```POST users/{userId}/facebook```][+](legacy-status)

[```POST users/{userId}/favorites/albums```][+](user-add-favorite-album)

[```POST users/{userId}/favorites/artists```][+](user-add-favorite-artist)

[```POST users/{userId}/favorites/playlists```][+](user-add-favorite-playlist)

[```POST users/{userId}/favorites/tracks```][+](user-add-favorite-track)

[```POST users/{userId}/favorites/videos```][+](user-add-favorite-video)

[```POST users/{userId}/clients/{clientId}/offline/albums```][+](legacy-status)

[```POST users/{userId}/clients/{clientId}/offline/playlists```][+](legacy-status)

[```POST users/{userId}/playlists```][+](user-create-playlist)

[```GET users/facebook/acceptedEULA```][+](legacy-status)

[```GET users/{userId}/clients```][+](user-clients)

[```GET users/{userId}/favorites/ids```][+](user-ids)

[```GET users/{userId}/favorites/albums```][+](user-favorite-albums)

[```GET users/{userId}/favorites/artists```][+](user-favorite-artists)

[```GET users/{userId}/playlistsAndFavoritePlaylists```][+](user-playlists-&-favorite-playlists)

[```GET users/{userId}/favorites/playlists```][+](user-favorite-playlists)

[```GET users/{userId}/favorites/tracks```][+](user-favorite-tracks)

[```GET users/{userId}/favorites/videos```][+](user-favorite-videos)

[```GET users/{userId}/handovertoken```][+](legacy-status)

[```GET users/{userId}/clients/{clientId}/offline/albums```][+](user-offline-albums)

[```GET users/{userId}/clients/{clientId}/offline/playlists```][+](user-offline-playlists)

[```DELETE users/{userId}/clients/{clientId}/offline/all```][+](user-delete-offline-all)

[```DELETE users/{userId}/facebook```][+](legacy-status)

[```DELETE users/{userId}/favorites/albums/{albumId}```][+](user-delete-favorite-album)

[```DELETE users/{userId}/favorites/artists/{artistId}```][+](user-delete-favorite-artist)

[```DELETE users/{userId}/favorites/playlists/{uuid}```][+](user-delete-favorite-playlist)

[```DELETE users/{userId}/favorites/tracks/{trackId}```][+](user-delete-favorite-track)

[```DELETE users/{userId}/favorites/videos/{videoId}```][+](user-delete-favorite-video)

[```DELETE users/{userId}/clients/{clientId}/offline/albums/{albumId}```][+](user-delete-offline-album)

[```DELETE users/{userId}/clients/{clientId}/offline/playlists/{playlistUuid}```][+](user-delete-offline-playlist)

[```POST users/{userId}/subscription/updateWithAmazon```][+](legacy-status)

[```POST users/{userId}/image```][+](user-image-update)

[```GET users/{userId}/playlists```][+](user-playlists)

[```GET sessions```][+](sessions)

[```GET v2/user-playlists/{userId}/public```][+](user-playlists-public)

[```GET v2/profiles/{userId}```][+](user-profile)

[```GET users/{userId}/activity```][+](user-activity)

[```GET users/{userId}/blocks/ids```][+](user-blocks)

[```GET users/{userId}/blocks/{type}```][+](user-blocks)

[```POST users/{userId}/blocks/{type}```][+](user-blocks)

[```DELETE users/{userId}/blocks/{type}/{id}```][+](user-blocks)

[```GET users/{userId}/onboarding```][+](user-onboarding)

[```POST users/{userId}/onboarding```][+](user-onboarding)

[```POST users/{userId}/earlyAccessProgram```][+](user-onboarding)

[```GET v2/my-collection/artists```][+](my-collection-artists)

[```GET v2/marketplace/v1/user-purchases```][+](marketplace)

[```GET v2/marketplace/spotlight/v1/user```][+](marketplace)

[```POST v2/marketplace/v3/checkout```][+](marketplace)

[```GET v2/favorites/mixes```][+](user-favorite-mixes)

[```PUT v2/favorites/mixes/add```][+](user-add-favorite-mix)

[```PUT v2/favorites/mixes/remove```][+](user-delete-favorite-mix)
###### My Collection (v2)
[```GET v2/my-collection/playlists/folders```][+](my-collection-folders)

[```PUT v2/my-collection/playlists/folders/create-playlist```][+](my-collection-create-playlist)

[```PUT v2/my-collection/playlists/folders/create-folder```][+](my-collection-create-folder)

[```PUT v2/my-collection/playlists/folders/add-favorites```][+](user-add-favorite-playlist)

[```PUT v2/my-collection/playlists/folders/rename```][+](my-collection-rename-folder)

[```PUT v2/my-collection/playlists/folders/move```][+](my-collection-move)

[```PUT v2/my-collection/playlists/folders/remove```][+](my-collection-remove)
###### Pages
[```GET pages/home```][+](page-home)

[```GET pages/explore```][+](page-explore)

[```GET pages/videos```][+](page-videos)

[```GET pages/mix```][+](page-mix)

[```GET pages/my_collection_my_mixes```][+](page-mymixes)

[```GET pages/artist```][+](page-artist)

[```GET pages/album```][+](page-album)

[```GET pages/for_you```][+](page-for-you)

[```GET pages/hires```][+](page-hires)

[```GET pages/genre_page```][+](page-genre)

[```GET pages/moods```][+](page-moods)

[```GET v2/home/feed/static```][+](home-feed-static)

[```GET v2/home/feed/{vibe}```][+](home-feed-vibe)

[```GET v2/home/pages/{moduleId}/view-all```][+](home-feed-vibe)
###### Search
[```GET search/albums```][+](search-albums)

[```GET search/artists```][+](search-artists)

[```GET search/playlists```][+](search-playlists)

[```GET search```][+](search)

[```GET search/tracks```][+](search-tracks)

[```GET search/videos```][+](search-videos)

[```GET v2/search```][+](search-v2)

[```GET v2/client-search```][+](search-v2)

[```GET v2/suggestions```][+](search-suggestions)

[```DELETE v2/suggestions```][+](search-suggestions)
###### Widevine

[```POST drm/licenses/widevine```][+](legacy-status)

[```POST v2/widevine```][+](drm)

[```POST streamingprivileges/tokens```][+](legacy-status)

[```POST rt/connect```][+](streaming-privileges)

###### Authentication
[```POST oauth2/token```][+](auth-token)

[```GET authorize```][+](auth-pkce)

[```POST web-session/credentials```][+](web-session)

[```POST web-session/logout```][+](web-session)

[```POST oauth2/device_authorization```][+](auth-device_authorization)

[```GET users/{userId}/loginToken```][+](loginToken)

[```POST login/username```][+](auth-username-password)

[```POST logout```][+](log-out)

[```GET authorize``` (login.tidal.com)][+](auth-pkce)

###### Miscellaneous
[```GET country```][+](country)

[```GET genres```][+](genres)

[```GET ping```][+](country)

[```GET v2/images/metadata-and-process```][+](images-metadata)

[```GET welcome/categories/artists```][+](welcome-artists)

[```POST welcome/users/artists```][+](welcome-artists)

[```GET v2/onboarding/tmm/migration```][+](onboarding-v2)

[```POST v2/chat/init```][+](music-assistant)

[```POST tidal.com/api/event-batch```][+](event-batch)
###### Cloud Queue (connectqueue.tidal.com/v1)
[```POST queues```][+](cloud-queue)

[```GET queues/{queueId}```][+](cloud-queue)

[```GET queues/{queueId}/items```][+](cloud-queue)

[```PUT queues/{queueId}/items```][+](cloud-queue)

[```PATCH queues/{queueId}/items```][+](cloud-queue)

[```DELETE queues/{queueId}/items/{itemId}```][+](cloud-queue)

[```PUT queues/{queueId}/shuffle```][+](cloud-queue)

[```GET content/{queueId}```][+](cloud-queue)

###### Official TIDAL API
[List of all Official API Endpoints](official-endpoints)

###### Android app
All 271 private endpoints of the Android app (incl. the ones only the app uses, e.g. `my-activity`, `my-collection/albums|artists|mixes`, `profiles`, `follow`, `tasks`, `googleplay`, `broadcasts`) with test status: [List of all Android Endpoints](android-endpoints)
