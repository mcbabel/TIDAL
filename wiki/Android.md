The TIDAL Android app (package `com.aspiro.tidal`, internal code name *WiMP/aspiro*) uses the same backends as the web player, plus a few Android-only services.

Analysed version: **2.215.0** (versionCode 10019, Play Store build, pulled 2026-11-01 from a phone with `adb`). The HTTP layer is OkHttp + Retrofit; every endpoint below was taken from the Retrofit interfaces in the app and then called against the live API (see [Android Endpoints](android-endpoints) and [Test Report](TestReport)).

* 271 private API operations in 100+ service interfaces (`com.aspiro.wamp.*`, `com.tidal.android.*`)
* 390 operations of the [Official TIDAL API](OfficialAPI), generated client `com.tidal.sdk.tidalapi.generated.apis.*`. All of them are part of the public OpenAPI spec (nothing hidden).

##### Hosts used by the app
| Host | Used for |
|---|---|
| `https://api.tidal.com/v1/` | Catalog, user, playlists, pages, playback info (videos), sessions, onboarding flags |
| `https://api.tidal.com/v2/` | My Collection (albums, artists, mixes, playlists), profiles, follow, my-activity, home feed, artist page, search suggestions, uploads, marketplace, chat, offline albums |
| `https://api.tidal.com/v2/onboarding/` | Setup guide (`tasks`) |
| `https://openapi.tidal.com/v2/` | [Official TIDAL API](OfficialAPI) (playback manifests, user collections, play queues, …) |
| `https://auth.tidal.com/v1/` | OAuth2 (`oauth2/token`, `oauth2/device_authorization`), Play Integrity nonce, one-time token (`ipt`) |
| `https://login.tidal.com/` | Login page (PKCE) |
| `https://connectqueue.tidal.com/v1/` | [Cloud Queue](cloud-queue) (TIDAL Connect) |
| `https://sonos.tidal.com/v1/sonos/cloudqueue/` | Sonos cloud queue (`items/{groupId}`) |
| `https://pulsar.tidal.com/` | Event / play log upload (`api/event-batch`, `api/public/event-batch`) |
| `https://fsu.fa.tidal.com/storage/` | File storage, referenced by the upload feature (not callable on its own) |
| `https://ec.tidal.com` | Referenced by the app; answers `403` to direct requests, purpose not verified |
| `wss://pushkin-v2.tidal.com/…` | [Streaming Privileges](streaming-privileges) WebSocket |
| `https://resources.tidal.com/images/…`, `/videos/…` | Images and animated covers |
| `https://offer.tidal.com`, `https://account.tidal.com` | Sign up / account pages (opened in the browser) |

Staging hosts exist as `*.stage.tidal.com` (not used in production builds).

##### Headers and query parameters added to every request
Found in the OkHttp interceptors of the app:

| Interceptor | Adds |
|---|---|
| User agent | ```User-Agent: TIDAL_ANDROID/{versionCode} {okhttp user agent}``` (e.g. `TIDAL_ANDROID/10019 okhttp/…`) and ```x-tidal-client-version: {versionName}``` (e.g. `2.215.0`) |
| Device | Query parameters `deviceType` (`PHONE`, `TABLET`, `AUTOMOTIVE` for Android Auto/Automotive), `locale` and **`platform=ANDROID`** |
| Client token | ```X-Tidal-Token: {client_id}``` and `countryCode` for requests without user |
| Authorization | ```Authorization: Bearer {access_token}```; refreshes the token depending on the `subStatus` of a `401` |
| Play Integrity | ```PI-Token: {integrity token}``` and ```PI-Package-Name: com.aspiro.tidal``` on selected requests (see below) |
| Official API | ```Idempotency-Key: {uuid}``` on writes |

The v2 page endpoints (`artist/{id}`, `home/feed/{vibe}`, `…/view-all`, `artist/{id}/playable`) answer `400 Bad Request` without the `platform` parameter (verified 2026-11; `platform=ANDROID` and `platform=WEB` both work).

##### Login
* The app logs in with **Authorization Code + PKCE** ([auth-pkce](auth-pkce)). Its `redirect_uri` is `https://tidal.com/android/login/auth`: after the login on `login.tidal.com` TIDAL redirects there with `?code=…`, Android hands the URL to the app (App Link), and the app exchanges the code at [`oauth2/token`](auth-token). Opened in a browser the page shows "page not found" (verified 2026-11).
* Also implemented: [Device flow](auth-device_authorization) (TV/limited input), `grant_type=refresh_token`, `client_credentials`, `update_client` (token upgrade with `client_unique_key`), `user_auth_token` and an exchange of a legacy `session_id` (fields `user_id`, `session_id`, `client_unique_key`, `client_id`, `scope`) for OAuth tokens.
* **Play Integrity:** `GET https://auth.tidal.com/v1/playintegrity/nonce` returns `{"nonce": "…"}` (verified 2026-11). The app asks Google Play Integrity for a token bound to this nonce and sends it as `PI-Token` header. Play Integrity is Google's mechanism to prove that a request comes from the genuine app on a genuine device.
* **One-time token:** `POST https://auth.tidal.com/v1/ipt` (form encoded, verified to exist: `GET` answers `405`) issues a one-time token (`OneTimeTokenService`); not executed, see [Test Report](TestReport).

##### Playback
* Tracks are played through the official API ([`trackManifests`](official-trackManifests), Widevine, see [DRM](drm)); videos can also use `videoManifests`. The app contains no `tracks/{id}/playbackinfo` call anymore.
* Videos still use [`videos/{id}/playbackinfopostpaywall`](video-playbackinfopostpaywall) (v1) with `playbackmode`, `assetpresentation`, `videoquality`, `streamingsessionid`, `playlistuuid`.
* DJ sessions: [`broadcasts/{djSessionId}/playbackinfo`](broadcast-playbackinfo).
* Widevine licenses are requested at the `licenseUrl` from the manifest; the legacy `POST v1/drm/licenses/widevine` is still referenced but answers `500` (verified 2026-11).
* Offline: see [Offline (Android)](android-offline).

##### Android-only features
* [My Activity](my-activity) (listening statistics, top artists, timeline)
* [My Collection v2](my-collection-v2) for albums, artists and mixes
* [Profiles & Follow](profiles)
* [Setup Guide](setup-guide)
* [Upload & Creator](upload-creator)
* [Google Play / Operator billing](android-billing)
* [App URLs & Properties](app-urls)
* [Experiments & Feature Flags](experiments)

See [Android Endpoints](android-endpoints) for the full list with test status.
