Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A task describing an offline sync action for a user's device.

#### Resource `offlineTasks`
| Attribute | Type | Description |
|---|---|---|
| `action` | string (STORE, REMOVE) | Action to perform |
| `position` | integer (int32) | Collection position of item |
| `state` | string (PENDING, IN_PROGRESS, FAILED, COMPLETED) | Task state |
| `volume` | integer (int32) | Collection volume of item |

Relationships (`include=`): `collection`, `item`, `owners`

### Get multiple offlineTasks
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/offlineTasks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple offlineTasks by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[installation.id]` | query | yes | string[] | List of offline task IDs (e.g. `a468bee88def`) |
| `include` | query |  | string[] | Include related resources. Available relationships: collection, item, owners |
| `includeLinkage` | query |  | string[]: collection, item, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: collection |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single offlineTask
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/offlineTasks/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single offlineTask by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Offline task id |
| `include` | query |  | string[] | Include related resources. Available relationships: collection, item, owners |
| `includeLinkage` | query |  | string[]: collection, item, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: collection |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single offlineTask
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/offlineTasks/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Updates existing offlineTask.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Offline task id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "state": "PENDING | IN_PROGRESS | FAILED | COMPLETED"
    },
    "id": "string",
    "type": "offlineTasks"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get collection relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/offlineTasks/{id}/relationships/collection```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves collection relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Offline task id |
| `include` | query |  | string[] | Include related resources. Available relationships: collection |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: collection |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get item relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/offlineTasks/{id}/relationships/item```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves item relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Offline task id |
| `include` | query |  | string[] | Include related resources. Available relationships: item |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: item |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/offlineTasks/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Offline task id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
