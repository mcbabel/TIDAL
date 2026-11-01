Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A module within a dynamic page, containing resources to render. Page composition may vary with client context; module resources do not.

#### Resource `dynamicModules`
| Attribute | Type | Description |
|---|---|---|
| `headerActions` | string[] (SPOTLIGHT_INFO, UNKNOWN) | Actions available in the module header. SPOTLIGHT_INFO opens information about TIDAL Spotlight. Clients choose the presentation and ignore unsupported actions, including UNKNOWN. |
| `previewLayout` | string (GRID, LIST, SHORTCUT, UNKNOWN) | Presentation family for items in a dynamic module preview. The API selects the semantic presentation intent while clients own platform-specific geometry. A layout does not prescribe scroll direction, row or column count, dimensions, spacing, breakpoints, or visible item count; clients preserve the server-provided item order. GRID means artwork-forward tiles or cards. LIST means detail-forward row cells, which clients may arrange in one or more columns. SHORTCUT means compact quick-access items, which clients may arrange as a responsive grid or rail. UNKNOWN is the forward-compatible default; clients should skip the module or use a safe default. |
| `subtitle` (optional) | string | Subtitle of the module |
| `title` (optional) | string | Title of the module |
| `viewAllLayout` (optional) | string (GRID, LIST, UNKNOWN) | Presentation family for items on a dynamic module's view-all screen. The API selects the semantic presentation intent while clients own platform-specific geometry. A layout does not prescribe scroll direction, row or column count, dimensions, spacing, or breakpoints; clients preserve the server-provided item order. When viewAllLayout is omitted, the module has no view-all screen. GRID means artwork-forward tiles or cards. LIST means detail-forward row cells, which clients may arrange in one or more columns or as a table. UNKNOWN is the forward-compatible default; clients should skip the module or use a safe default. |

Relationships (`include=`): `items`, `seedItem`

### Get multiple dynamicModules
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicModules```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple dynamicModules by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `filter[id]` | query | yes | string[] | DynamicModules Id (e.g. `nejMcAhh5N8S3EQ4LaqysVdI0cZZ`) |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: items, seedItem |
| `includeLinkage` | query |  | string[]: items, seedItem | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single dynamicModule
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicModules/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single dynamicModule by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `id` | path | yes | string | DynamicModules Id |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: items, seedItem |
| `includeLinkage` | query |  | string[]: items, seedItem | Comma-separated direct relationships to return as linkage only, without related content. |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicModules/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

The module's items, in order — one stable collection per module, consistent for a given refreshSeed. Reads without a cursor return the first page (the slice a page shelf renders, sized for the module's previewLayout and device) with a continuation cursor; passing the cursor returns subsequent pages.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `id` | path | yes | string | DynamicModules Id |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get seedItem relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/dynamicModules/{id}/relationships/seedItem```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

The item whose listen or add event seeded this module's collection (e.g. the album a BECAUSE_YOU_* module is based on); null for modules that are not seeded by an item.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `clientVersion` | query | yes | string | Client version number |
| `deviceType` | query | yes | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `id` | path | yes | string | DynamicModules Id |
| `systemType` | query | yes | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: seedItem |
| `locale` | query |  | string | BCP 47 locale (e.g., en-US, nb-NO, pt-BR). Defaults to en-US if not provided or unsupported. |
| `refreshSeed` | query |  | string | Stable seed used to keep dynamic page and module results consistent across a client session. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: seedItem |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
