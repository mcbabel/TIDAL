Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A music genre classification.

#### Resource `genres`
| Attribute | Type | Description |
|---|---|---|
| `genreName` | string | Genre name |

### Get multiple genres
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/genres```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves multiple genres by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | Allows filtering by genre id(s). USER_SELECTABLE is special value used to return specific genres which users can select from (e.g. `'1,2,3' or 'USER_SELECTABLE'`) |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single genre
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/genres/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single genre by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Genre id |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
