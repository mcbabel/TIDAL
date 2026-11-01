Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Playback statistics for a track, including total plays and unique listeners.

#### Resource `trackStatistics`
| Attribute | Type | Description |
|---|---|---|
| `totalPlaybacks` | integer (int32) | Total playbacks |
| `uniqueListeners` | integer (int32) | Unique listeners |

Relationships (`include=`): `owners`

### Get single trackStatistic
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackStatistics/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single trackStatistic by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track statistic id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackStatistics/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track statistic id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
