#### Example Request (verified 2026-11)
* Credits page of an artist (all tracks the artist contributed to, grouped by role). Web player route: `/credits/{artistId}`.
* Same page/rows/modules format as [Get Page Home](page-home).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/contributor?artistId={id}&countryCode={country}&deviceType={enum}&locale={locale}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response
``` yaml
{
  "selfLink": null,
  "id": "xxxxxxxxxxxx",
  "title": "...",
  "rows": [ ... ]
}
```
