Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A short-lived login link for the Stripe Express dashboard.

#### Resource `stripeDashboardLinks`
| Attribute | Type | Description |
|---|---|---|
| `dashboardLink` (optional) | Link_Object | A JSON:API link object |

Relationships (`include=`): `owners`

### Get multiple stripeDashboardLinks
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/stripeDashboardLinks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple stripeDashboardLinks by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/stripeDashboardLinks/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Stripe dashboard link id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
