Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user-submitted report flagging inappropriate or harmful content.

#### Resource `userReports`
| Attribute | Type | Description |
|---|---|---|
| `description` | string | Description |
| `reason` | string (SEXUAL_CONTENT_OR_NUDITY, VIOLENT_OR_DANGEROUS_CONTENT, HATEFUL_OR_ABUSIVE_CONTENT, HARASSMENT, PRIVACY_VIOLATION, SCAMS_OR_FRAUD, SPAM, COPYRIGHT_INFRINGEMENT, APPEAL, UNKNOWN) | Reason |

### Create single userReport
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userReports```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new userReport.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "description": "string",
      "reason": "SEXUAL_CONTENT_OR_NUDITY | VIOLENT_OR_DANGEROUS_CONTENT | HATEFUL_OR_ABUSIVE_CONTENT | HARASSMENT | PRIVACY_VIOLATION | SCAMS_OR_FRAUD | SPAM | COPYRIGHT_INFRINGEMENT | APPEAL | UNKNOWN"
    },
    "relationships": {
      "reportedResources": {
        "data": [
          {
            "id": "string",
            "type": "tracks | artists | playlists"
          }
        ]
      }
    },
    "type": "userReports"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
