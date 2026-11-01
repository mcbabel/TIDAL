#### Example Request (verified 2026-11)
* Search of the Android app (`com.aspiro.tidal` 2.215.0): result lists per type plus `topHits` (ranked mix of all types).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/search/top-hits?query={query}&types={types}&limit={limit}&offset={offset}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "artists": { … },
  "albums": { … },
  "playlists": { … },
  "tracks": { … },
  "videos": { … },
  "genres": [ … ],
  "topHits": [ … ]
}
```
