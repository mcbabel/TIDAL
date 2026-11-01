Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user-owned folder. Its contents are folderItems: folders, albums and references to things shared with the caller. Start at GET /folders/me, the caller's root folder, and walk down through /folders/me/relationships/children.

#### Resource `folders`
| Attribute | Type | Description |
|---|---|---|
| `isRoot` | boolean | Whether this is the root folder. |
| `name` | string |  |

Relationships (`include=`): `children`, `owners`, `parent`, `preview`, `shares`

### Get multiple folders
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves multiple folders by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | Folder id (e.g. `e3226624-355b-48f8-aa93-db42532caa66`). Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: children, owners, parent, preview, shares |
| `includeLinkage` | query |  | string[]: children, owners, parent, preview, shares | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: children.subject |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single folder
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/folders```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Creates a new folder.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "name": "string"
    },
    "relationships?": {
      "parent?": {
        "data": {
          "id": "string",
          "type": "folders"
        }
      }
    },
    "type": "folders"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single folder
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/folders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Deletes existing folder.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single folder
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves single folder by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: children, owners, parent, preview, shares |
| `includeLinkage` | query |  | string[]: children, owners, parent, preview, shares | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: children.subject |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single folder
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/folders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Updates existing folder.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "name": "string"
    },
    "id": "string",
    "type": "folders"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get children relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}/relationships/children```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Lists folder items newest first by placement timestamp, with ID as a stable tie-breaker. Moving to another parent resets the timestamp; renaming preserves it.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: children |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: children.subject |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get parent relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}/relationships/parent```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves parent relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: parent |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: parent.children.subject |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get preview relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}/relationships/preview```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

The first four items of this folder, as `children` lists them.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: preview |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: preview.subject |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get shares relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/folders/{id}/relationships/shares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

The folder's share links, active and expired, newest first.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: shares |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: shares.sharedResources |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
