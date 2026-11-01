Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A Square seller connection linked to a user for receiving payments.

#### Resource `squareConnections`
| Attribute | Type | Description |
|---|---|---|
| `capabilities` (optional) | SquareConnections_Capability[] | Per-feature capability statuses for this Square connection. Every capability the connection offers is listed with a status carrying more than mere presence: SITES is GRANTED when the Square Online sites scopes are granted, or REQUIRES_REAUTH when the connection exists but its credential lacks them (the seller must reconnect Square via POST /squareConnections). Because a connection always offers the sites feature, SITES is always present here. Extensible — only SITES is defined today. Absent only when the connection has no sites state (e.g. no approved Square credential). Client rule: if SITES != GRANTED prompt reconnect; else if selectedSite.data is null show the site picker; else the selected site is shown to buyers. |
| `createdAt` (optional) | string (date-time) | Timestamp when the connection was created |
| `externalLinks` (optional) | External_Link[] | External links for Square connection |
| `lastModifiedAt` (optional) | string (date-time) | Timestamp when the connection was last modified |
| `status` | string (DRAFT, PENDING_REQUIREMENTS, KYC_PENDING, ACCEPTED, REJECTED, SUSPENDED) | Current status of this Square connection |

Relationships (`include=`): `selectedSite`, `sites`

### Create single squareConnection
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/squareConnections```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new squareConnection.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "type": "squareConnections"
  },
  "meta": {
    "platform": "WEB | ANDROID | IOS",
    "redirectUrl?": "string"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single squareConnection
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareConnections/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single squareConnection by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square connection id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: selectedSite, sites |
| `includeLinkage` | query |  | string[]: selectedSite, sites | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get selectedSite relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareConnections/{id}/relationships/selectedSite```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves selectedSite relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square connection id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: selectedSite |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update selectedSite relationship ("to-one")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareConnections/{id}/relationships/selectedSite```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Replaces the selected Square site. Explicit null data clears the selection without deleting the site. Returns the selected site linkage, or null data when cleared.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square connection id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "id": "string",
    "type": "squareSites"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get sites relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareConnections/{id}/relationships/sites```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves sites relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square connection id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: sites |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
