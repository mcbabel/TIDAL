### Get Home Feed By Vibe (verified 2026-11)
* The tabs at the top of the home page (`header.vibes` of [Home Feed](home-feed-static)). `STATIC` is the default "For you" feed.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/home/feed/{vibe}?countryCode={country}&locale={locale}&deviceType={enum}&platform=WEB&timeOffset={offset}```
##### vibe Enums (seen 2026-11)
```STATIC```\
```EDITORIAL``` (Staff Picks)\
```UPLOADS```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```\
```x-tidal-experiment-visitor-id: {uuid}``` (optional)
#### Example Response
Same format as [Home Feed](home-feed-static).

### Get Home View All (verified 2026-11)
* "View all" list of a home module (path from the module's `viewAll` field), e.g. `LATEST_SPOTLIGHTED_TRACKS`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/home/pages/{moduleId}/view-all?limit={limit}&offset={offset}&countryCode={country}&locale={locale}&deviceType={enum}&platform=WEB```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "title": "Spotlighted Uploads",
  "subtitle": "Independent tracks selected by Tidal's editorial team. Listen now for free.",
  "itemLayout": "COMPACT",
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
