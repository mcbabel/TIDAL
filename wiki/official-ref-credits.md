Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A credit entry linking a contributor to a track or album.

#### Resource `credits`
| Attribute | Type | Description |
|---|---|---|
| `name` | string | Credit name |
| `role` | string | Credit role |

Relationships (`include=`): `artist`, `category`

### Get single credit
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/credits/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404`.

Retrieves single credit by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Credit id |
| `include` | query |  | string[] | Include related resources. Available relationships: artist, category |
| `includeLinkage` | query |  | string[]: artist, category | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/credits/{id}/relationships/artist```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404`.

Retrieves artist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Credit id |
| `include` | query |  | string[] | Include related resources. Available relationships: artist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get category relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/credits/{id}/relationships/category```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404`.

Retrieves category relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Credit id |
| `include` | query |  | string[] | Include related resources. Available relationships: category |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
