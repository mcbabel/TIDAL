Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's collection of favorited albums.

#### Resource `userCollectionAlbums`
| Attribute | Type | Description |
|---|---|---|
| `lastModifiedAt` (optional) | string (date-time) | When the collection was last modified |
| `numberOfItems` | integer (int32) | Number of items in the collection |

Relationships (`include=`): `items`, `owners`

### Get single userCollectionAlbum
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userCollectionAlbums/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves single userCollectionAlbum by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection albums id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: items, owners |
| `includeLinkage` | query |  | string[]: items, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from items relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userCollectionAlbums/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Deletes item(s) from items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection albums id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "albums"
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
```https://openapi.tidal.com/v2/userCollectionAlbums/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection albums id. Use `me` for the authenticated user's resource |
| `filter[query]` | query |  | string | Filter albums by a free-text query matched against the album title and artist names. Internal clients only (e.g. `love`) |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
| `sort` | query |  | string[]: addedAt, -addedAt, artists.name, -artists.name, releaseDate, -releaseDate, title, -title | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to items relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userCollectionAlbums/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `collection.write`, `w_usr`

Adds item(s) to items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection albums id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta?": {
        "addedAt?": "string (date-time)"
      },
      "type": "albums"
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
```https://openapi.tidal.com/v2/userCollectionAlbums/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `collection.read`, `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User collection albums id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
