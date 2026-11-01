Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Streaming statistics of an artist over one reporting window. listeners, newFollowers and saves count unique listeners, new followers and saves in the window, each with its own status. breakdownsStatus covers playsBySource, topCountries and the entries of topTracks. When it is not OK, playsBySource and topCountries are absent and topTracks has empty linkage with the status in its meta, because its entries are withheld.

#### Resource `artistStreamsStatistics`
| Attribute | Type | Description |
|---|---|---|
| `breakdownsStatus` | string (OK, SUPPRESSED, UNAVAILABLE) | Status of artist statistics that may be withheld. OK: the data is present. SUPPRESSED: withheld because too few people are counted to show it. UNAVAILABLE: not available at the moment |
| `dataThrough` | string (date) | Last day included in the underlying data |
| `endDate` | string (date) | Last day of the window, inclusive |
| `lastModifiedAt` | string (date-time) | When these statistics were computed |
| `listeners` | ArtistStreamsStatistics_Count | A count in the window that may be withheld. value is present exactly when status is OK, and 0 is a measured zero |
| `newFollowers` | ArtistStreamsStatistics_Count | A count in the window that may be withheld. value is present exactly when status is OK, and 0 is a measured zero |
| `plays` | ArtistStreamsStatistics_Plays |  |
| `playsBySource` (optional) | ArtistStreamsStatistics_PlaysBySource | Plays by where they started. other holds the plays not in items. Without a note, items and other add up to all plays, and an absent other means no plays are left. With note HIDDEN, part of the plays is withheld, so an absent other is unknown rather than zero |
| `saves` | ArtistStreamsStatistics_Count | A count in the window that may be withheld. value is present exactly when status is OK, and 0 is a measured zero |
| `series` | ArtistStreamsStatistics_Series | Plays per bucket |
| `startDate` | string (date) | First day of the window |
| `topCountries` (optional) | ArtistStreamsStatistics_TopCountries | Listeners by country. Without a note, items and otherListeners add up to all listeners, and an absent otherListeners means no listeners are left. With note HIDDEN, part of the listeners is withheld, so an absent otherListeners is unknown rather than zero |
| `windowPeriod` | ArtistStatisticsWindowPeriod (P7D, P28D, P12M) | Reporting window preset. startDate and endDate give the actual data coverage |

Relationships (`include=`): `artist`, `topTracks`

### Get multiple artistStreamsStatistics
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistStreamsStatistics```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple artistStreamsStatistics by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[artist.id]` | query | yes | string[] | Artist ID. Every published range of the artist is returned (e.g. `1566`) |
| `include` | query |  | string[] | Include related resources. Available relationships: artist, topTracks |
| `includeLinkage` | query |  | string[]: artist, topTracks | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistStreamsStatistics/{id}/relationships/artist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves artist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist streams statistics id |
| `include` | query |  | string[] | Include related resources. Available relationships: artist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get topTracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistStreamsStatistics/{id}/relationships/topTracks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves topTracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist streams statistics id |
| `include` | query |  | string[] | Include related resources. Available relationships: topTracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: topTracks |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
