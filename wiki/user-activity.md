#### Example Request (verified 2026-11)
* Recent activity of the user (e.g. playlists created or updated).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/activity?limit={limit}&offset={offset}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 60,
  "items": [
    {
      "activityType": "UPDATED",
      "time": "2026-10-30T23:57:36.716+0000",
      "type": "PLAYLIST",
      "item": {
        "uuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "title": "...",
        ...
      }
    }
  ]
}
```
