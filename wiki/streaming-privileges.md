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

#### Update 2026-11: Test status
`rt/connect` verified (`200`, WebSocket url). The WebSocket messages are taken from the web player code. They were not provoked on purpose, because that needs a second device that starts playback on the same account.

#### Update 2026-11: verified with two devices
While the web player was playing, playback was started on a second device of the same account. The open WebSocket received:
``` yaml
{
  "payload": {
    "clientDisplayName": "Web",
    "sessionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  },
  "type": "PRIVILEGED_SESSION_NOTIFICATION"
}
```
The player paused immediately and showed "Playback was paused because you are playing something on Web". `clientDisplayName` is the name of the device that took over, `sessionId` identifies its session. The client did not send `USER_ACTION` in this test (it is sent on certain user interactions only).
