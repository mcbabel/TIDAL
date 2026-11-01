Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

The authenticated user's unread and seen state for each feed surface.

#### Resource `userFeeds`
| Attribute | Type | Description |
|---|---|---|
| `feed` | UserFeeds_Attributes_Feed | Feed read state |
| `inbox` | UserFeeds_Attributes_Inbox | Inbox read state |

### Get single userFeed
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userFeeds/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single userFeed by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of a user's feed state. Use `me` for the authenticated user's resource |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single userFeed
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/userFeeds/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Advances the supplied seen positions and returns the updated feed state.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Opaque identifier of a user's feed state. Use `me` for the authenticated user's resource |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "feed?": {
        "seenThroughToken": "string"
      },
      "inbox?": {
        "seenThroughToken": "string"
      }
    },
    "id": "string",
    "type": "userFeeds"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
