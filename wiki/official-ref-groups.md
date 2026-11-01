Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A platform-managed audience. The Everyone group includes eligible callers with or without an end-user identity and has no stored member roster.

#### Resource `groups`
| Attribute | Type | Description |
|---|---|---|
| `name` | string | Group name |

### Get multiple groups
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/groups```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves multiple groups by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[name]` | query | yes | string | Exact group name (case-sensitive) (e.g. `Everyone`) |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single group
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/groups/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single group by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Group ID |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
