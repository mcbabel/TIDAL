Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A registered device installation for a user.

#### Resource `installations`
| Attribute | Type | Description |
|---|---|---|
| `clientProvidedInstallationId` | string | Client provided installation identifier |
| `name` | string | Human-readable name for the installation |

Relationships (`include=`): `offlineInventory`, `owners`

### Get multiple installations
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/installations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple installations by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[clientProvidedInstallationId]` | query |  | string[] | Client-provided installation identifier to filter by (e.g. `a468bee88def`) |
| `filter[owners.id]` | query |  | string[] | User ID to filter by. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: offlineInventory, owners |
| `includeLinkage` | query |  | string[]: offlineInventory, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single installation
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/installations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new installation.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "clientProvidedInstallationId": "string",
      "name": "string"
    },
    "type": "installations"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single installation
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/installations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single installation by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Installation id |
| `include` | query |  | string[] | Include related resources. Available relationships: offlineInventory, owners |
| `includeLinkage` | query |  | string[]: offlineInventory, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from offlineInventory relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/installations/{id}/relationships/offlineInventory```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from offlineInventory relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Installation id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | videos | albums | playlists | userCollectionTracks"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get offlineInventory relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/installations/{id}/relationships/offlineInventory```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves offlineInventory relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[type]` | query | yes | string[]: tracks, videos, albums, playlists, userCollectionTracks | One of: tracks, videos, albums, playlists, userCollectionTracks (e.g. `tracks`) |
| `id` | path | yes | string | Installation id |
| `filter[id]` | query |  | string[] | Offline item id (e.g. `1234`) |
| `filter[state]` | query |  | string[]: PENDING, STORED, FAILED | One of: PENDING, STORED, FAILED (e.g. `PENDING`) |
| `include` | query |  | string[] | Include related resources. Available relationships: offlineInventory |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to offlineInventory relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/installations/{id}/relationships/offlineInventory```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to offlineInventory relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Installation id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | videos | albums | playlists | userCollectionTracks"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/installations/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Installation id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
