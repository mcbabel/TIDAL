#### Example Request (verified 2026-11)
* Returns userId and countryCode of the current access_token
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/sessions```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
```yaml
{
  "sessionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "userId": 123456789,
  "countryCode": "DE",
  "channelId": 123,
  "partnerId": 1,
  "client": {
    "id": 123456789,
    "name": "{client name}",
    "authorizedForOffline": false,
    "authorizedForOfflineDate": null
  }
}
```

#### Update 2026-11: Android app (verified)
* `GET https://api.tidal.com/v1/sessions/{sessionId}` returns the same object for a given session id (`200`).
* The Android app also exchanges legacy `session_id`s for OAuth tokens, see [Android](Android).
