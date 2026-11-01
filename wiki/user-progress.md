#### Example Request (verified 2026-11)
* Playback progress (resume position) of long items. Returned an empty list for the tested track.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/progress/items?ids={id},{id}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
[]
```
