#### Example Request (verified 2026-11)
* Like [Get Album Items](album-items), but only tracks and without the `{"item": ..., "type": ...}` wrapper.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/albums/{id}/tracks?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 17,
  "items": [
    {
      "id": 38519995,
      "title": "...",
      ...
    }
  ]
}
```
