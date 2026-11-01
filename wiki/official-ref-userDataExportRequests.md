Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A request to export a user's personal data collected by Tidal.

#### Resource `userDataExportRequests`
| Attribute | Type | Description |
|---|---|---|
| `flowType` | string (GDPR, CCPA, COPPA, ANZ_PA, US_PRIVACY_REGULATION, APPI, RETENTION_POLICY) | The type of data export flow |

### Create single userDataExportRequest
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/userDataExportRequests```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new userDataExportRequest.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "flowType": "GDPR | CCPA | COPPA | ANZ_PA | US_PRIVACY_REGULATION | APPI | RETENTION_POLICY"
    },
    "type": "userDataExportRequests"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
