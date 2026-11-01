Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's save-for-later collection.

#### Resource `userCollectionSaveForLaters`
| Attribute | Type | Description |
|---|---|---|
| `lastModifiedAt` (optional) | string (date-time) | When the collection was last modified |
| `numberOfItems` | integer (int32) | Number of items in the collection |

Relationships (`include=`): `items`, `owners`

### Get single userCollectionSaveForLater
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionSaveForLaters/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single userCollectionSaveForLater by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection save for later id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: items, owners |
| `includeLinkage` | query |  | string[]: items, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from items relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userCollectionSaveForLaters/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection save for later id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | albums | artists | playlists | videos"
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
```https://openapi.tidal.com/v2/userCollectionSaveForLaters/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection save for later id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to items relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userCollectionSaveForLaters/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection save for later id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | albums | artists | playlists | videos"
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
```https://openapi.tidal.com/v2/userCollectionSaveForLaters/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection save for later id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
