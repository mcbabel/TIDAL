TIDAL used to allow direct Username and Password logins with a SessionId exchange. The endpoint still exists but all new client_ids (Tokens) disabled direct session based logins. Still there are a few working tokens for legacy app support (old iOS and FireTV apps). Just recently TIDAL disabled the client_id for the legacy android app.

##### Update 2026-11
* **Username & Password login**: no longer possible, use the [DeviceFlow](Authentication) or [Authorization Code + PKCE](auth-pkce).
* **MQA / `HI_RES`** (July 2024): replaced by `HI_RES_LOSSLESS` (FLAC up to 24bit/192kHz). Requests with `HI_RES` are answered with `HI_RES_LOSSLESS`. See [Audio Quality](AudioQuality).
* **Sony 360 Reality Audio** (`SONY_360RA`): removed in 2024.
* **`tracks/{id}/streamUrl`, `tracks/{id}/urlpostpaywall`**: answer `401 subStatus 4005 "Asset is not ready for playback"` (verified 2026-11). Use [PlaybackInfo](track-playbackinfo). The video variants still work.
* **`listen.tidal.com`**: redirects to `tidal.com`. The web player uses the proxy `tidal.com/v1` / `tidal.com/v2`.
* **`pages/home`, `pages/artist`**: still work, but the apps now use [Home Feed](home-feed-static) and [Artist Page v2](artist-page-v2).
* **`GET users/{id}/favorites/mixes`**: does not exist (404), use [Get User Favorite Mixes](user-favorite-mixes) (v2).
* **Subscription types `HIFI` / `HIFI_PLUS`**: replaced by `FREE` / `PREMIUM`.

