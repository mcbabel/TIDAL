Status of the private endpoints that were listed in this documentation but never documented (former "This Endpoint is not yet documented" entries). Checked on 2026-11-01.

| Endpoint | Status |
|---|---|
| ```POST playlists/{uuid}/items/{index}/replace``` | Documented: [Replace Playlist Item](playlist-replace-item) (verified) |
| ```POST drm/licenses/widevine``` | Replaced by ```POST https://api.tidal.com/v2/widevine```, see [DRM](drm) |
| ```POST streamingprivileges/tokens``` | Answers `403` (verified). Replaced by [Streaming Privileges](streaming-privileges) (`POST v1/rt/connect` + WebSocket) |
| ```POST users/{userId}/playlists``` | Documented: [Create Playlist (v1)](user-create-playlist) (verified) |
| ```GET authorize``` | Documented: [Authorization Code + PKCE](auth-pkce) |
| ```GET country``` | Documented: [Get Country](country) (verified) |
| ```GET users/facebook/acceptedEULA``` | Answers `404 subStatus 2001` (verified). Removed. |
| ```POST users/{userId}/facebook```, ```DELETE users/{userId}/facebook``` | Not used by any current client we inspected. Facebook login is handled by login.tidal.com. Considered removed. |
| ```POST users/{userId}/subscription/updateWithAmazon``` | Not used by the web player. Only relevant for in-app purchases on Amazon devices. Not verifiable without such a device. |
| ```GET users/{userId}/handovertoken``` | Not used by the web player (it uses [Web Session](web-session) instead). Not verified: it issues a login credential. |
| ```POST users/{userId}/clients/{clientId}/offline/albums```, ```.../offline/playlists``` | Offline downloads of the mobile/desktop apps. Need a client that is `authorizedForOffline` ([Get User Clients](user-clients)). The web player has no offline mode, so these could not be verified. The official API has internal equivalents: `installations/{id}/relationships/offlineInventory` and `offlineTasks`, see [Official API Endpoints](official-endpoints). |

##### Coverage method
* Test status of every endpoint: [Test Report](TestReport).
* All API calls in the JavaScript of the web player (version 2026.10.31, 128 files) were extracted and compared with this documentation. Every private endpoint found there is documented.
* All 438 operations of the official OpenAPI spec 1.10.218 are documented (generated reference pages). All 309 official API paths used by the web player are part of the spec.
* Endpoints that only exist in the mobile, desktop or TV apps cannot be found this way.

##### Update 2026-11: Android app
* `GET users/{userId}/handovertoken` answers `200 {"value": "…"}` both with the web session token and with a real app token (verified 2026-11; the value was never printed or stored).
* `DELETE users/{userId}/favorites/mixes/{mixId}/remove` and `GET users/{userId}/favorites/mixes` (v1) are still in the app but answer `404`; use [My Collection v2](my-collection-v2) / [Favorite Mixes](user-favorite-mixes).
* Offline albums/playlists per device are used by the Android app; see [Offline (Android)](android-offline).
