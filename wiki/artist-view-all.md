#### Example Request (verified 2026-11)
* "View all" list of a module of the [Artist Page v2](artist-page-v2). The module's `viewAll` field contains the path, e.g. `artist/ARTIST_ALBUMS/view-all?artistId=3529689`.
* Optional: `itemId`
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/artist/{sourceType}/view-all?artistId={id}&limit={limit}&offset={offset}&countryCode={country}&locale={locale}&deviceType={enum}&platform=WEB```
##### sourceType Enums (seen 2026-11)
```ARTIST_TOP_TRACKS```\
```ARTIST_ALBUMS```\
```ARTIST_TOP_SINGLES``` (EP & Singles)\
```ARTIST_COMPILATIONS```\
```ARTIST_LIVE_ALBUMS```\
```ARTIST_PLAYLIST```\
```ARTIST_SIMILAR_ARTISTS```\
```ARTIST_CREDITS```\
```ARTIST_APPEARS_ON```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "title": "Top Tracks",
  "subtitle": "...",
  "itemLayout": "...",
  "filters": [],
  "items": [
    {
      "type": "TRACK",
      "following": false,
      "data": { ... }
    }
  ],
  "description": "..."
}
```
