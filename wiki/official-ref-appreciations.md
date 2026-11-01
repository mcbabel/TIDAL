Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's appreciation of a piece of content.

#### Resource `appreciations`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) | Time when the appreciation was created |

### Create single appreciation
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/appreciations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new appreciation.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "appreciatedItems": {
        "data": [
          {
            "id": "string",
            "type": "artists"
          }
        ]
      }
    },
    "type": "appreciations"
  },
  "meta?": {
    "dryRun?": "boolean"
  }
}
```
`?` = optional
##### Responses
`200` Successful dry run, `201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
