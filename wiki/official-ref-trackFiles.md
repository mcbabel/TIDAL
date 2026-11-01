Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An individual audio file for a track in a specific format and quality.

#### Resource `trackFiles`
| Attribute | Type | Description |
|---|---|---|
| `albumAudioNormalizationData` (optional) | AudioNormalizationData | Track normalization data |
| `format` (optional) | string (HEAACV1, AACLC, FLAC, FLAC_HIRES, EAC3_JOC) | File's audio format |
| `trackAudioNormalizationData` (optional) | AudioNormalizationData | Track normalization data |
| `trackPresentation` (optional) | string (FULL, PREVIEW) | Track presentation |
| `url` (optional) | string | File URL |

### Get single trackFile
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackFiles/{id}```
##### Access
Tier: `PARTNER` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `playback`, `r_usr`

**Live test 2026-11-01:** answered `403` `CLIENT_NOT_ENTITLED: Client cannot access this content`.

Retrieves single trackFile by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `formats` | query | yes | string[]: HEAACV1, AACLC, FLAC, FLAC_HIRES, EAC3_JOC |  |
| `id` | path | yes | string | Track file id |
| `usage` | query | yes | string: PLAYBACK, DOWNLOAD |  |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
