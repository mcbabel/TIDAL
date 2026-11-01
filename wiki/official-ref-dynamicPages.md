Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A dynamically composed page of modules, such as the home screen.

#### Resource `dynamicPages`
| Attribute | Type | Description |
|---|---|---|
| `pageType` | string (HOME_STATIC, HOME_UPLOADS, HOME_EDITORIAL, HOME_FREE, STUDIO_HOME, ARTIST, ALBUM, PLAYLIST, TRACK, VIDEO) | Type of the page eg. home, artist |
| `reportingId` | string (uuid) | Id used for reporting user events |

Relationships (`include=`): `modules`, `subject`

### Get multiple dynamicPages
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicPages```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple dynamicPages by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `filter[pageType]` | query | yes | string[]: HOME_STATIC, HOME_UPLOADS, HOME_EDITORIAL, HOME_FREE, STUDIO_HOME, ARTIST, ALBUM, PLAYLIST, TRACK, VIDEO | Type of the page (e.g. `ARTIST`) |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[subject]` | query |  | string | The page subject. Its type must match pageType. Required except for HOME_FREE, where it must be omitted. Also accepts `users:me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: modules, subject |
| `includeLinkage` | query |  | string[]: modules, subject | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: modules.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get modules relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicPages/{id}/relationships/modules```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

The page's modules, in display order.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `id` | path | yes | string | DynamicPages Id |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: modules |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: modules.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get subject relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicPages/{id}/relationships/subject```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves subject relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | DynamicPages Id |
| `include` | query |  | string[] | Include related resources. Available relationships: subject |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: subject |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
