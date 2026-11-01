Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Status of metadata detection job for a track. Tracks the progress of async jobs that detect and pre-fill metadata fields.

#### Resource `tracksMetadataStatus`
| Attribute | Type | Description |
|---|---|---|
| `status` | string (PENDING, PROCESSING, ERROR, OK) | Status of the metadata detection job |

### Get single tracksMetadataStatu
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracksMetadataStatus/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`.

Retrieves single tracksMetadataStatu by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Tracks metadata status id |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
