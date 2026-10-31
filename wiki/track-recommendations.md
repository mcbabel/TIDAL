#### Example Request (verified 2026-11)
* Needs a user. With `x-tidal-token` the endpoint answers `401 Missing auth parameter`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/recommendations?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 20,
  "items": [
    {
      "track": {
        "id": 0,
        "title": "1997 (Exit A)",
        ...
      },
      "sources": [
        "SUGGESTED_TRACKS"
      ]
    }
  ]
}
```
