#### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}?countryCode={country}&include={relationships}```
##### Relationships (include)
```albums```, ```artists```, ```owners```, ```providers```, ```radio```, ```similarTracks```, ```sourceFile```, ```usageRules``` (third-party)
##### Header
```Authorization: Bearer {access_token}``` (Client Credentials or PKCE)\
```Accept: application/vnd.api+json```
#### Example Response

``` yaml
{
  "data": {
    "id": "38519997",
    "type": "tracks",
    "attributes": {
      "title": "Object 3",
      "version": null,
      "isrc": "DEZ750500205",
      "duration": "PT2M4S",
      "copyright": {
        "text": "Alien Transistor"
      },
      "explicit": false,
      "ai": false,
      "key": "Ab",
      "keyScale": "MAJOR",
      "bpm": 78,
      "popularity": 0.3427244789802435,
      "accessType": "PUBLIC",
      "availability": [
        "STREAM",
        "DJ"
      ],
      "mediaTags": [
        "HIRES_LOSSLESS",
        "LOSSLESS"
      ],
      "toneTags": [],
      "externalLinks": [
        {
          "href": "https://tidal.com/browse/track/38519997",
          "meta": {
            "type": "TIDAL_SHARING"
          }
        }
      ],
      "spotlighted": false,
      "createdAt": "2014-12-03T13:23:18Z"
    },
    "relationships": {
      "albums": {
        "data": [
          {
            "id": "38519994",
            "type": "albums"
          }
        ],
        "links": {
          "self": "/tracks/38519997/relationships/albums?countryCode=DE"
        }
      },
      "artists": {
        "data": [
          {
            "id": "3529689",
            "type": "artists"
          }
        ],
        "links": {
          "self": "/tracks/38519997/relationships/artists?countryCode=DE"
        }
      }
    }
  },
  "links": {
    "self": "/tracks/38519997?include=albums%2Cartists&countryCode=DE"
  },
  "included": [
    {
      "id": "38519994",
      "type": "albums",
      "attributes": {
        "title": "Messier Objects",
        "barcodeId": "880918220925",
        "numberOfVolumes": 1,
        "numberOfItems": 17,
        "duration": "PT54M13S",
        "explicit": false,
        ...
      }
    },
    {
      "id": "3529689",
      "type": "artists",
      "attributes": {
        "name": "The Notwist",
        "popularity": 0.6804727833634698,
        "numberOfFollowers": 9753,
        ...
      }
    }
  ]
}
```
#### Notes
* `availability` is deprecated, use the `usageRules` relationship.
* Multiple tracks: `GET /tracks?filter[id]=1,2,3` or by ISRC `GET /tracks?filter[isrc]=DEZ750500205` (one ISRC can return several tracks).
* Albums by barcode: `GET /albums?filter[barcodeId]=880918220925`
