Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A content provider or label that supplies music to TIDAL.

#### Resource `providers`
| Attribute | Type | Description |
|---|---|---|
| `name` | string | Provider name |

### Get single provider
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/providers/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single provider by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Provider ID |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
