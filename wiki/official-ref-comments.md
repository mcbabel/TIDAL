Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

#### Resource `comments`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) | Datetime when the comment was created (ISO 8601) |
| `endTime` (optional) | string | End time offset for timestamped comments (ISO 8601 duration) |
| `lastModifiedAt` | string (date-time) | Datetime when the comment was last modified (ISO 8601) |
| `likeCount` | integer (int32) | Number of likes on this comment |
| `message` | string | The comment message content |
| `moderationStatus` | string (NOT_MODERATED, FLAGGED, TAKEN_DOWN, OK, ERROR) | Moderation status of the comment |
| `replyCount` | integer (int32) | Number of replies to this comment |
| `startTime` (optional) | string | Start time offset for timestamped comments (ISO 8601 duration) |

Relationships (`include=`): `author`, `owners`, `parentComment`

### Get multiple comments
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/comments```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** answered `404`.

Retrieves multiple comments by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[parentComment.id]` | query |  | string[] | Filter by parent comment ID to get replies (e.g. `550e8400-e29b-41d4-a716-446655440000`) |
| `filter[subject.id]` | query |  | string[] | Deprecated: use filter[subject]. Filter by subject resource ID (e.g. `12345`) **Deprecated.** |
| `filter[subject.type]` | query |  | string[]: albums, tracks, trackSourceFiles | Deprecated: use filter[subject]. Filter by subject resource type (e.g. `albums`) **Deprecated.** |
| `filter[subject]` | query |  | string | The subject whose comments to return. Use either subject or the deprecated subject.id and subject.type pair. |
| `include` | query |  | string[] | Include related resources. Available relationships: author, owners, parentComment |
| `includeLinkage` | query |  | string[]: author, owners, parentComment | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: author.albums |
| `sort` | query |  | string[]: createdAt, -createdAt, likeCount, -likeCount, replyCount, -replyCount, startTime, -startTime | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single comment
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/comments```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Comments can only be posted on albums, tracks and uploads of other people. They are public and the artist is notified.

Creates a new comment.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "endTime?": "string",
      "message": "string",
      "startTime?": "string"
    },
    "relationships": {
      "parentComment?": {
        "data": {
          "id": "string",
          "type": "comments"
        }
      },
      "subject": {
        "data": {
          "id": "string",
          "type": "albums | tracks | trackSourceFiles"
        }
      }
    },
    "type": "comments"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single comment
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/comments/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing comment.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single comment
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/comments/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** not reached. The account has no comments (creating one is not done, see `POST /comments`).

Retrieves single comment by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `include` | query |  | string[] | Include related resources. Available relationships: author, owners, parentComment |
| `includeLinkage` | query |  | string[]: author, owners, parentComment | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: author.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single comment
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/comments/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing comment.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "endTime?": "string",
      "message?": "string",
      "startTime?": "string"
    },
    "id": "string",
    "type": "comments"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get author relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/comments/{id}/relationships/author```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** not reached. The account has no comments (creating one is not done, see `POST /comments`).

The artist who wrote the comment.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `include` | query |  | string[] | Include related resources. Available relationships: author |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: author.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/comments/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** not reached. The account has no comments (creating one is not done, see `POST /comments`).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get parentComment relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/comments/{id}/relationships/parentComment```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** not reached. The account has no comments (creating one is not done, see `POST /comments`).

Retrieves parentComment relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Comment Id |
| `include` | query |  | string[] | Include related resources. Available relationships: parentComment |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: parentComment.author.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
