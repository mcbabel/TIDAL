#### Example Request (verified 2026-11)
* Search of the current apps. Needs a user token (without: `400 "Token is missing"`, subStatus 11002). For anonymous search use [Search All](search).
* Each result list has `items`, `totalNumberOfItems` and `cacheable`. `topHits` is a list of `{"type": ..., "value": {...}}`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/search/?query={query}&limit={limit}&offset={offset}&types={types}&includeContributors=true&includeDidYouMean=true&includeUserPlaylists=true&supportsUserData=true&countryCode={country}&locale={locale}&deviceType={enum}```
##### types
```ARTISTS```, ```ALBUMS```, ```TRACKS```, ```VIDEOS```, ```PLAYLISTS```, ```USERPROFILES```, ```UPLOADS```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "artists": {
    "items": [
      {
        "id": 3529689,
        "name": "The Notwist",
        ...
      }
    ],
    "totalNumberOfItems": 129,
    "cacheable": true
  },
  "albums": { ... },
  "tracks": { ... },
  "videos": { ... },
  "playlists": { ... },
  "uploads": { ... },
  "genres": [],
  "contentTypeFilters": [
    "ARTISTS",
    "ALBUMS",
    "TRACKS",
    "UPLOADS",
    "PLAYLISTS",
    "VIDEOS"
  ],
  "topHits": [
    {
      "type": "ARTISTS",
      "value": {
        "id": 3529689,
        "name": "The Notwist",
        ...
      }
    }
  ],
  "queryId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
}
```
