Offline downloads of the Android app (`com.aspiro.tidal` 2.215.0). The web player has no offline mode.

### Get Offline Albums (v2) (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/offline/albums```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [],
  "cursor": null
}
```

### Authorize Device For Offline (not executed)
* Deauthorize: `DELETE v1/users/{userId}/clients/offline/{clientId}`. Needs the client id of an app installation; the test account had no device client ([Get User Clients](user-clients) returned none).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/clients/offline```
##### Url-Encoded POST Parameter
```clientId: {clientId}```\
```name: {device name}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

### Report Offline Plays (not executed)
* Uploads plays that happened offline. Not executed: it would add fake plays to the statistics.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/report/offlineplays```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/json```

Offline albums and playlists per device: [Get User Offline Albums](user-offline-albums), [Get User Offline Playlists](user-offline-playlists) and the delete endpoints (need an offline-authorized device). The official API has `installations` and `offlineTasks` for the same purpose.

#### Update 2026-11: Test status (verified with a real TV app token)
Tested with a TV-client user token (device flow): `POST users/{userId}/clients/offline` (authorize the client for offline) answers `403`, and the offline-album endpoints then still answer `400 subStatus 1002`. So offline authorization is not available through this API even with a genuine app token; it is tied to the native app installation (Play Integrity). `DELETE users/{userId}/clients/offline/{clientId}` (deauthorize) answers `204` (idempotent).