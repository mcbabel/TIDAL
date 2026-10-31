#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/artists?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)\
```order={enum}```\
```orderDirection={enum}```
##### Order Enums
```DATE```\
```NAME```\
```ARTIST```\
```RELEASE_DATE```
##### OrderDirection Enums
```ASC```\
```DESC```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 10,
  "items": [
    {
      "created": "2019-11-16T20:32:44.750+0000",
      "item": {
        "id": 13979,
        "name": "Brad Mehldau",
        "artistTypes": [
          "ARTIST",
          "CONTRIBUTOR"
        ],
        "url": "http://www.tidal.com/artist/13979",
        "picture": "15e9f535-7c0a-494b-b36e-5cdc9f41f1f5",
        "popularity": 54,
        "artistRoles": [
          {
            "categoryId": -1,
            "category": "Artist"
          },
          {
            "categoryId": 11,
            "category": "Performer"
          },
          {
            "categoryId": 2,
            "category": "Songwriter"
          },
          {
            "categoryId": 1,
            "category": "Producer"
          },
          {
            "categoryId": 10,
            "category": "Production team"
          }
        ],
        "mixes": {
          "MASTER_ARTIST_MIX": "0158e64f0c0b6f2d80a9577ca33393",
          "ARTIST_MIX": "00099811c1d038ffb45edc9d3e52d1"
        }
      }
    },
    {
      "created": "2020-05-31T21:22:12.375+0000",
      "item": {
        "id": 3840013,
        "name": "Chilly Gonzales",
        "artistTypes": [
          "ARTIST",
          "CONTRIBUTOR"
        ],
        "url": "http://www.tidal.com/artist/3840013",
        "picture": "78bf245a-e471-4bb1-bf0f-b94e5dd80832",
        "popularity": 44,
        "artistRoles": [
          {
            "categoryId": -1,
            "category": "Artist"
          },
          {
            "categoryId": 2,
            "category": "Songwriter"
          },
          {
            "categoryId": 11,
            "category": "Performer"
          },
          {
            "categoryId": 1,
            "category": "Producer"
          },
          {
            "categoryId": 10,
            "category": "Production team"
          },
          {
            "categoryId": 3,
            "category": "Engineer"
          }
        ],
        "mixes": {
          "MASTER_ARTIST_MIX": "0152670a8aa47447591905f99828c5",
          "ARTIST_MIX": "000e50b4b7914a9f2ae234b8e4893c"
        }
      }
    }
  ]
}
```
