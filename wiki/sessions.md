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
