Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Represents a folder for organizing items in a user's collection.

#### Resource `userCollectionFolders`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) |  |
| `lastModifiedAt` | string (date-time) |  |
| `name` | string |  |
| `numberOfItems` (optional) | integer (int32) |  |

Relationships (`include=`): `items`, `owners`, `userCollection`

### Get multiple userCollectionFolders
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves multiple userCollectionFolders by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | Folder Id (e.g. `CBMHXUOuJZgroV2kWpeVLL1I7xdgvF6ocDEGCXov8SZq3WVhrOcOq5pjnGawKX`) |
| `include` | query |  | string[] | Include related resources. Available relationships: items, owners, userCollection |
| `includeLinkage` | query |  | string[]: items, owners, userCollection | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single userCollectionFolder
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Creates a new userCollectionFolder.
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
    "relationships": {
      "userCollection": {
        "data": {
          "id": "string",
          "type": "userCollectionPlaylists"
        }
      }
    },
    "type": "userCollectionFolders"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single userCollectionFolder
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Deletes existing userCollectionFolder.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single userCollectionFolder
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves single userCollectionFolder by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `include` | query |  | string[] | Include related resources. Available relationships: items, owners, userCollection |
| `includeLinkage` | query |  | string[]: items, owners, userCollection | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single userCollectionFolder
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Updates existing userCollectionFolder.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "name": "string"
    },
    "id": "string",
    "type": "userCollectionFolders"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete from items relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Deletes item(s) from items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data?": [
    {
      "id": "string",
      "type": "playlists"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items.items |
| `sort` | query |  | string[]: addedAt, -addedAt, lastModifiedAt, -lastModifiedAt, name, -name | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to items relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Adds item(s) to items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data?": [
    {
      "id": "string",
      "type": "playlists"
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
```https://openapi.tidal.com/v2/userCollectionFolders/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get userCollection relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionFolders/{id}/relationships/userCollection```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves userCollection relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Folder Id |
| `include` | query |  | string[] | Include related resources. Available relationships: userCollection |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: userCollection.items.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
