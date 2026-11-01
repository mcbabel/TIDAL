Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An OAuth scope that a client may request from end users.

#### Resource `scopes`
| Attribute | Type | Description |
|---|---|---|
| `consentText` (optional) | string | Text shown to the end user on the OAuth consent screen when this scope is requested. |
| `description` | string | Technical description of the scope. |
| `name` | string | Wire-format scope name as used in OAuth requests. |
| `requiredAccessTier` | string (THIRD_PARTY, THIRD_PARTY_PROD, PARTNER, INTERNAL) | Client access tier required to request this scope. A client whose access tier is at least this value can include the scope when initiating an OAuth flow. |

### Get multiple scopes
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/scopes```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple scopes by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[requiredAccessTier]` | query | yes | string[]: THIRD_PARTY, THIRD_PARTY_PROD, PARTNER, INTERNAL | Filters scopes by their `requiredAccessTier`. (e.g. `THIRD_PARTY`) |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
