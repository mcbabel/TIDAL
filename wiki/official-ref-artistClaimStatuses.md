Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Claim status for an artist profile.

#### Resource `artistClaimStatuses`
| Attribute | Type | Description |
|---|---|---|
| `claimSources` | string[] (ARTIST_CLAIMS, MANUAL_ARTIST_CLAIMS) | Claim sources contributing to the current status. Empty when there is no active claim. |
| `status` | string (CLAIM_IN_PROGRESS, NO_ACTIVE_CLAIM) | Whether the artist profile currently has an active claim |

### Get multiple artistClaimStatuses
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaimStatuses```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves multiple artistClaimStatuses by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | List of artist claim status IDs (e.g. `QVJUSVNUUzoxNTY2`) |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
