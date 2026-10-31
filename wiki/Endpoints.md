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

[```POST playlists/{uuid}/items/{index}/replace```][+](404)

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
[```POST users/{userId}/facebook```][+](404)

[```POST users/{userId}/favorites/albums```][+](user-add-favorite-album)

[```POST users/{userId}/favorites/artists```][+](user-add-favorite-artist)

[```POST users/{userId}/favorites/playlists```][+](user-add-favorite-playlist)

[```POST users/{userId}/favorites/tracks```][+](user-add-favorite-track)

[```POST users/{userId}/favorites/videos```][+](user-add-favorite-video)

[```POST users/{userId}/clients/{clientId}/offline/albums```][+](404)

[```POST users/{userId}/clients/{clientId}/offline/playlists```][+](404)

[```POST users/{userId}/playlists```][+](404)

[```GET users/facebook/acceptedEULA```][+](404)

[```GET users/{userId}/clients```][+](user-clients)

[```GET users/{userId}/favorites/ids```][+](user-ids)

[```GET users/{userId}/favorites/albums```][+](user-favorite-albums)

[```GET users/{userId}/favorites/artists```][+](user-favorite-artists)

[```GET users/{userId}/playlistsAndFavoritePlaylists```][+](user-playlists-&-favorite-playlists)

[```GET users/{userId}/favorites/playlists```][+](user-favorite-playlists)

[```GET users/{userId}/favorites/tracks```][+](user-favorite-tracks)

[```GET users/{userId}/favorites/videos```][+](user-favorite-videos)

[```GET users/{userId}/handovertoken```][+](404)

[```GET users/{userId}/clients/{clientId}/offline/albums```][+](user-offline-albums)

[```GET users/{userId}/clients/{clientId}/offline/playlists```][+](user-offline-playlists)

[```DELETE users/{userId}/clients/{clientId}/offline/all```][+](user-delete-offline-all)

[```DELETE users/{userId}/facebook```][+](404)

[```DELETE users/{userId}/favorites/albums/{albumId}```][+](user-delete-favorite-album)

[```DELETE users/{userId}/favorites/artists/{artistId}```][+](user-delete-favorite-artist)

[```DELETE users/{userId}/favorites/playlists/{uuid}```][+](user-delete-favorite-playlist)

[```DELETE users/{userId}/favorites/tracks/{trackId}```][+](user-delete-favorite-track)

[```DELETE users/{userId}/favorites/videos/{videoId}```][+](user-delete-favorite-video)

[```DELETE users/{userId}/clients/{clientId}/offline/albums/{albumId}```][+](user-delete-offline-album)

[```DELETE users/{userId}/clients/{clientId}/offline/playlists/{playlistUuid}```][+](user-delete-offline-playlist)

[```POST users/{userId}/subscription/updateWithAmazon```][+](404)

[```POST users/{userId}/image```][+](user-image-update)

[```GET users/{userId}/playlists```][+](user-playlists)

[```GET sessions```][+](sessions)

[```GET v2/user-playlists/{userId}/public```][+](user-playlists-public)

[```GET v2/profiles/{userId}```][+](user-profile)

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
###### Search
[```GET search/albums```][+](search-albums)

[```GET search/artists```][+](search-artists)

[```GET search/playlists```][+](search-playlists)

[```GET search```][+](search)

[```GET search/tracks```][+](search-tracks)

[```GET search/videos```][+](search-videos)

[```GET v2/search```][+](search-v2)
###### Widevine

[```POST drm/licenses/widevine```][+](404)

[```POST streamingprivileges/tokens```][+](404)

###### Authentication
[```POST oauth2/token```][+](auth-token)

[```GET authorize```][+](404)

[```POST oauth2/device_authorization```][+](auth-device_authorization)

[```GET users/{userId}/loginToken```][+](loginToken)

[```POST login/username```][+](auth-username-password)

[```POST logout```][+](log-out)

[```GET authorize``` (login.tidal.com)][+](auth-pkce)

###### Miscellaneous
[```GET country```][+](country)

[```GET genres```][+](genres)

[```GET ping```][+](country)

###### Official TIDAL API
[List of all Official API Endpoints](official-endpoints)
