Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An association between a content provider and an owning user.

#### Resource `providerOwners`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) |  |

Relationships (`include=`): `owners`, `provider`

### Get multiple providerOwners
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerOwners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple providerOwners by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, provider |
| `includeLinkage` | query |  | string[]: owners, provider | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerOwners/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Provider owner id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get provider relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providerOwners/{id}/relationships/provider```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves provider relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Provider owner id |
| `include` | query |  | string[] | Include related resources. Available relationships: provider |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
