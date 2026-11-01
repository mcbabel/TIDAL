Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's remote-control playback state.

#### Resource `userPlaybackStates`
| Attribute | Type | Description |
|---|---|---|
| `playbackStatus` | string (IDLE, PLAYING, PAUSED) |  |

Relationships (`include=`): `activePlayer`, `availablePlayers`, `changeEventStream`, `playQueue`

### Get single userPlaybackState
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single userPlaybackState by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: activePlayer, availablePlayers, changeEventStream, playQueue |
| `includeLinkage` | query |  | string[]: activePlayer, availablePlayers, changeEventStream, playQueue | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: activePlayer.offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single userPlaybackState
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a Base62-encoded user ID`. Not executed for real: it changes the playback state of the account (would take over or interrupt playback on the user’s devices).

Updates existing userPlaybackState.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "playbackStatus?": "PLAYING | PAUSED"
    },
    "id": "string",
    "type": "userPlaybackStates"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get activePlayer relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/activePlayer```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves activePlayer relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: activePlayer |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: activePlayer.offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update activePlayer relationship ("to-one")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/activePlayer```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a Base62-encoded user ID`. Not executed for real: it changes the playback state of the account (would take over or interrupt playback on the user’s devices).

Replaces the active-player selection with the supplied owned installation. Explicit null data releases the player without deleting the installation. Returns null linkage when released or when the selected installation has no live attachment. An unavailable selection is retained and becomes visible again when its attachment is refreshed.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "id": "string",
    "type": "installations"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete from availablePlayers relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/availablePlayers```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a Base62-encoded user ID`. Not executed for real: it changes the playback state of the account (would take over or interrupt playback on the user’s devices).

Detaches one installation without deleting it. Also releases the active player when it is that installation. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "installations"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get availablePlayers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/availablePlayers```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves availablePlayers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: availablePlayers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: availablePlayers.offlineInventory |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to availablePlayers relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/availablePlayers```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a Base62-encoded user ID`. Not executed for real: it changes the playback state of the account (would take over or interrupt playback on the user’s devices).

Attaches or refreshes one owned installation as an available player, preserving other attachments. Returns all currently available player linkage.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "installations"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get changeEventStream relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/changeEventStream```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves changeEventStream relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `include` | query |  | string[] | Include related resources. Available relationships: changeEventStream |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get playQueue relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/playQueue```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves playQueue relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: playQueue |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playQueue.current |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update playQueue relationship ("to-one")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/userPlaybackStates/{id}/relationships/playQueue```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a Base62-encoded user ID`. Not executed for real: it changes the playback state of the account (would take over or interrupt playback on the user’s devices).

Replaces the selected play queue. Explicit null data clears the selection without deleting the queue. Returns the selected queue linkage, or null data when cleared.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User playback session id. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "id": "string",
    "type": "playQueues"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
