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
