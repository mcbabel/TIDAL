Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A downloadable content file with its download links.

#### Resource `downloads`
| Attribute | Type | Description |
|---|---|---|
| `downloadLinks` (optional) | Download_Link[] |  |

Relationships (`include=`): `owners`

### Get multiple downloads
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/downloads```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple downloads by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | Download id (e.g. `VFJBQ0tTOjEyMzQ1`) |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single download
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/downloads/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single download by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Download id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/downloads/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Download id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
