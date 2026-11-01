Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's recommendation blocks for artists, tracks, and videos.

#### Resource `userRecommendationBlocks`
| Attribute | Type | Description |
|---|---|---|

Relationships (`include=`): `artists`, `owners`, `tracks`, `videos`

### Get single userRecommendationBlock
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

Retrieves single userRecommendationBlock by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: artists, owners, tracks, videos |
| `includeLinkage` | query |  | string[]: artists, owners, tracks, videos | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from artists relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get artists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

Retrieves artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: artists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to artists relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
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
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from tracks relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/tracks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from tracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get tracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/tracks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

Retrieves tracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: tracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: tracks |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to tracks relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/tracks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to tracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete from videos relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/videos```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from videos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "videos"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get videos relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/videos```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `recommendations.read`

Retrieves videos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: videos |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: videos |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to videos relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userRecommendationBlocks/{id}/relationships/videos```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to videos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User recommendation blocks id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "videos"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
