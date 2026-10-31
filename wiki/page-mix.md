#### Example Request (verified 2026-11)
* Page of a mix (header + track list). Use a current mix id, see [Get Mixes Items](mix-items).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/mix?mixId={mixId}&countryCode={country}&deviceType={enum}```
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
          "type": "MIX_HEADER",
          ...
        }
      ]
    },
    {
      "modules": [
        {
          "type": "TRACK_LIST",
          ...
        }
      ]
    }
  ]
}
```
