#### Example Request (verified 2026-11)
* Personal recommendations page.
* Same page/rows/modules format as [Get Page Home](page-home).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/for_you?countryCode={country}&deviceType={enum}&locale={locale}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Header
```authorization: Bearer {access_token}```
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
