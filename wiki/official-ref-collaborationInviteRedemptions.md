Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Deprecated compatibility view of accepting a COLLABORATOR playlist share. Use `savedShares` instead. Creating one saves the share and adds the caller as a collaborator. The returned ID identifies the same saved share.

#### Resource `collaborationInviteRedemptions`
| Attribute | Type | Description |
|---|---|---|
| `redeemedAt` | string (date-time) | Datetime the invite was redeemed (ISO 8601) |

### Create single collaborationInviteRedemption (Deprecated)
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/collaborationInviteRedemptions```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

Creates a new collaborationInviteRedemption.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "invite": {
        "data": {
          "id": "string",
          "type": "collaborationInvites"
        }
      }
    },
    "type": "collaborationInviteRedemptions"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
