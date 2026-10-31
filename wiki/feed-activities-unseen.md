#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/feed/activities/unseen/exists?userId={id}&countryCode={countryCode}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "hasUnseenActivities": false
}
```

#### Update 2026-11 (verified)
Still works. Current response: `{"hasUnseenActivities": false}`
