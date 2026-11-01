#### Example Request (verified 2026-11)
* Similar albums. Answers `404 "Similar albums for or album with id [{id}] not found"` if there are none (verified 2026-11). Verified with `200` for an album that has similar albums.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/albums/{id}/similar?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 10,
  "offset": 0,
  "totalNumberOfItems": 10,
  "items": [
    {
      "id": 38519994,
      "title": "Messier Objects",
      ...
    }
  ],
  "source": "TiVo"
}
```
