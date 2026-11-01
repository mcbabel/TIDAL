#### Example Request
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/feed/activities/seen?userId={id}&countryCode={countryCode}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
```200 No Error```

#### Update 2026-11 (verified)
Still works: `PUT` answers `200` with empty body. Send ```x-tidal-client-version: {version}```. Check first with [Get Activity Feed Unseen](feed-activities-unseen).
