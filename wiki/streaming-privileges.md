### Get Push Socket Url (verified 2026-11)
* TIDAL allows one active stream per account. The players connect to a WebSocket ("Pushkin") to learn when another device starts playing.
* Replaces the old `POST streamingprivileges/tokens` (answers `403` today, verified 2026-11).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/rt/connect```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/json```
#### Example Response
``` yaml
{
  "url": "wss://pushkin-v2.tidal.com/public/token/{token}/ws"
}
```

### WebSocket Messages (from web player code 2026-11)
Client → Server when the user starts playback:
``` yaml
{
  "type": "USER_ACTION",
  "payload": {
    "startedAt": 1793491228109
  }
}
```
Server → Client:
+ `PRIVILEGED_SESSION_NOTIFICATION` with `payload.clientDisplayName`: another device took over, the player pauses
+ `RECONNECT`: reconnect (request a new url)
