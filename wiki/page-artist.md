#### Example Request (verified 2026-11)
* Artist page (v1). The web player now uses [Get Artist Page v2](artist-page-v2).
* Same page/rows/modules format as [Get Page Home](page-home).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/artist?artistId={id}&countryCode={country}&deviceType={enum}&locale={locale}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "selfLink": null,
  "id": "xxxxxxxxxxxx",
  "title": "...",
  "rows": [
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "...",
          ...
        }
      ]
    }
  ]
}
```
