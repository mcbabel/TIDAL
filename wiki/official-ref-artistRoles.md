Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A role describing an artist's contribution, such as performer or producer.

#### Resource `artistRoles`
| Attribute | Type | Description |
|---|---|---|
| `name` | string | Name of the artist role |

### Get single artistRole
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistRoles/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single artistRole by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist role id |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
