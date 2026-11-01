Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's current play queue, including past and upcoming items.

#### Resource `playQueues`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) | ISO 8601 creation timestamp |
| `lastModifiedAt` | string (date-time) | ISO 8601 last modified timestamp |
| `repeat` | string (NONE, ONE, BATCH) | Queue's repeat mode |
| `revision` | string (uuid) | Opaque queue-wide equality token. |
| `shuffle` | string (OFF, BATCH, ALL) | Queue's shuffle mode |
| `shuffled` | boolean | Queue is shuffled or not |

Relationships (`include=`): `changeEventStream`, `current`, `future`, `owners`, `past`

### Get multiple playQueues
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple playQueues by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: changeEventStream, current, future, owners, past |
| `includeLinkage` | query |  | string[]: changeEventStream, current, future, owners, past | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: current |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single playQueue
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playQueues```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `201` (write test with cleanup).

Creates a new playQueue.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "type": "playQueues"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single playQueue
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Deletes existing playQueue.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single playQueue
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves single playQueue by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `include` | query |  | string[] | Include related resources. Available relationships: changeEventStream, current, future, owners, past |
| `includeLinkage` | query |  | string[]: changeEventStream, current, future, owners, past | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: current |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single playQueue
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Atomically applies attributes, future items, then current selection.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes?": {
      "repeat?": "NONE | ONE | BATCH",
      "shuffle?": "OFF | BATCH | ALL",
      "shuffled?": "boolean"
    },
    "id": "string",
    "relationships?": {
      "current?": {
        "meta": {
          "itemId?": "string",
          "mode": "FIRST_FUTURE_ITEM | ITEM"
        }
      },
      "future?": {
        "data": [
          {
            "id": "string",
            "type": "tracks | videos"
          }
        ],
        "meta": {
          "mode": "ADD_TO_FRONT | ADD_TO_BACK | ADD_BEFORE | REPLACE_ALL",
          "positionBefore?": "string",
          "source?": {
            "href": "string (uri-reference)",
            "startIndex": "integer (int32)"
          }
        }
      }
    },
    "type": "playQueues"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get changeEventStream relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/changeEventStream```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves changeEventStream relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `include` | query |  | string[] | Include related resources. Available relationships: changeEventStream |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get current relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/current```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves current relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `include` | query |  | string[] | Include related resources. Available relationships: current |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: current |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update current relationship ("to-one")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/current```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Sets the current item to the existing queue occurrence identified by data.meta.itemId, changing which entries are past and future. Null data is rejected. Optional position and updatedByInstallationId must be supplied together. Returns the current item linkage and queue revision.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "id": "string",
    "meta": {
      "itemId": "string",
      "position?": "string",
      "updatedByInstallationId?": "string"
    },
    "type": "tracks | videos"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete from future relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/future```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Removes the future occurrences selected by data[].meta.itemId without deleting their tracks or videos. Other queue entries are preserved. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "itemId": "string"
      },
      "type": "tracks | videos"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get future relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/future```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves future relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `include` | query |  | string[] | Include related resources. Available relationships: future |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: future |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update future relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/future```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Incrementally moves existing future occurrences selected by data[].meta.itemId, in their current queue order, before meta.positionBefore. Preserves memberships and unselected entries' metadata and relative order. Empty data is rejected. Returns empty data and meta.revision as an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "itemId": "string"
      },
      "type": "tracks | videos"
    }
  ],
  "meta": {
    "mode?": "INCREMENTAL",
    "positionBefore": "string"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Add to future relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/future```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Omitting top-level meta or setting it to null defaults to REPLACE_ALL, replacing future entries. Use ADD_TO_FRONT, ADD_TO_BACK or ADD_BEFORE in meta.mode to add without replacing existing entries. ADD_BEFORE requires meta.positionBefore. REPLACE_ALL_AND_CURRENT replaces future entries; ADD_TO_FRONT_REPLACE_CURRENT prepends entries. Both select the first newly inserted entry in the active queue order as current, which may differ from request order when shuffled. With empty data and no source, replacement modes clear future entries; the current entry is unchanged when no entries are inserted. With meta.source, startIndex selects an entry in the first page's data before unsupported types are skipped. Tracks and videos are added in page order, retaining duplicates; other types are skipped without expansion. Reaching 1000 added items or 100 pages queues the collected prefix. Invalid sources or indexes, a suffix with no playable items, repeated pages, and read failures encountered before a cap leave the queue unchanged. Returns empty data and meta.revision as an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | videos"
    }
  ],
  "meta?": {
    "batchId?": "string (uuid)",
    "legacySource?": {
      "id": "string",
      "type": "string"
    },
    "mode": "ADD_TO_FRONT | ADD_TO_BACK | ADD_BEFORE | REPLACE_ALL | REPLACE_ALL_AND_CURRENT | ADD_TO_FRONT_REPLACE_CURRENT",
    "positionBefore?": "string",
    "source?": {
      "href": "string (uri-reference)",
      "startIndex": "integer (int32)"
    }
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get past relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playQueues/{id}/relationships/past```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves past relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Play queue id |
| `include` | query |  | string[] | Include related resources. Available relationships: past |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: past |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
