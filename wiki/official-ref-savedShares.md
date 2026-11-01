Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A completed acceptance of a share's offered role.

#### Resource `savedShares`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) | Datetime of saved share creation (ISO 8601) |

### Create single savedShare
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/savedShares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Saves a share link of another user. Needs a share code from a different account, and there is no endpoint to remove a saved share.

Redeem an active share with VOUCHER access mode for its offered role. A share without VOUCHER mode returns 403.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "share": {
        "data": {
          "id": "string",
          "type": "shares"
        }
      }
    },
    "type": "savedShares"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
