#### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/artists/{id}/similar?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 1,
  "items": [
    {
      "id": 11083,
      "name": "Kings Of Convenience",
      "type": null,
      "artistTypes": [
        "ARTIST",
        "CONTRIBUTOR"
      ],
      "url": "http://www.tidal.com/artist/11083",
      "picture": "bc11f0f8-f744-4a38-889e-4ef5a9e740ac",
      "selectedAlbumCoverFallback": null,
      "popularity": 0,
      "banner": null,
      "artistRoles": null,
      "mixes": {
        "ARTIST_MIX": "000ce8b7919f940b096f20b99b737b"
      },
      "handle": null,
      "userId": null,
      "spotlighted": false,
      "relationType": "SIMILAR_ARTIST"
    }
  ],
  "source": "TiVo"
}
```
