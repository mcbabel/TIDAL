#### Example Request (observed 2026-11, also during playback)
* Analytics / play log events of the web player (TIDAL event producer). Logged-out visitors: `https://tidal.com/api/public/event-batch`.
##### Method
```POST```
##### Url
```https://tidal.com/api/event-batch```
##### Header
```authorization: Bearer {access_token}```
* Observed in the network traffic of the web player: `POST /api/event-batch` and `POST /api/public/event-batch` both answer `200`. Not sent manually: the events go into TIDAL's play statistics and analytics, fake events would distort them.
* During playback (logged in) the player sent `POST /api/event-batch` with `Authorization: Bearer {access_token}` about 2.7 s after start (31 KB) and again after about 15 s (3 KB), both `200`.
