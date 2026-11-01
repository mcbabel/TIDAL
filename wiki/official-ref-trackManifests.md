Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A playback manifest for a track, containing streaming URIs and format details.

#### Resource `trackManifests`
| Attribute | Type | Description |
|---|---|---|
| `albumAudioNormalizationData` (optional) | AudioNormalizationData | Track normalization data |
| `drmData` (optional) | DrmData | DRM data. Absence implies no DRM. |
| `formats` (optional) | string[] (HEAACV1, AACLC, FLAC, FLAC_HIRES, EAC3_JOC) | Formats present in manifest |
| `hash` (optional) | string | Unique manifest hash |
| `previewReason` (optional) | string (FULL_REQUIRES_SUBSCRIPTION, FULL_REQUIRES_PURCHASE, FULL_REQUIRES_HIGHER_ACCESS_TIER) | Why a preview is served instead of the full track |
| `trackAudioNormalizationData` (optional) | AudioNormalizationData | Track normalization data |
| `trackPresentation` (optional) | string (FULL, PREVIEW) | Track presentation |
| `uri` (optional) | string | Manifest URI |

### Get single trackManifest
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/trackManifests/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `playback`, `r_usr`

Retrieves single trackManifest by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `adaptive` | query | yes | boolean |  |
| `formats` | query | yes | string[]: HEAACV1, AACLC, FLAC, FLAC_HIRES, EAC3_JOC |  |
| `id` | path | yes | string | Track manifest id |
| `manifestType` | query | yes | string: HLS, MPEG_DASH |  |
| `uriScheme` | query | yes | string: HTTPS, DATA |  |
| `usage` | query | yes | string: PLAYBACK, DOWNLOAD |  |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
