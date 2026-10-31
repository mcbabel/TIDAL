#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/my_collection_my_mixes?countryCode={country}&deviceType={enums}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```

#### Example Response
```yaml
{
  "selfLink": null,
  "id": "xxxxxxxxxxxx",
  "title": "My Mix",
  "rows": [
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "MIX_LIST",
          "width": 100,
          "title": "",
          "description": "",
          "preTitle": null,
          "showMore": null,
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "VERTICAL",
          "listFormat": null,
          "pagedList": {
            "limit": 16,
            "offset": 0,
            "totalNumberOfItems": 14,
            "items": [
              {
                "id": "xxxxxxxxxxxx",
                "title": "My Mix 1",
                "subTitle": "Artist, Artist, Artist and more",
                "graphic": {
                  "type": "SQUARES_GRID",
                  "text": "MY MIX 1",
                  "images": [
                    {
                      "id": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                      "vibrantColor": "#8e473e",
                      "type": "ARTIST"
                    },
                    {
                      "id": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                      "vibrantColor": "#fda2a9",
                      "type": "ARTIST"
                    },
                    {
                      "id": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                      "vibrantColor": "#FFFFFF",
                      "type": "ARTIST"
                    },
                    {
                      "id": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                      "vibrantColor": "#FFFFFF",
                      "type": "ARTIST"
                    },
                    {
                      "id": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                      "vibrantColor": "#FFFFFF",
                      "type": "ARTIST"
                    }
                  ]
                },
                "images": {
                  "SMALL": {
                    "width": 320,
                    "height": 320,
                    "url": "https://images.tidal.com/0/xxxxxxxxxxxx"
                  },
                  "MEDIUM": {
                    "width": 640,
                    "height": 640,
                    "url": "https://images.tidal.com/0/xxxxxxxxxxxx0"
                  },
                  "LARGE": {
                    "width": 1500,
                    "height": 1500,
                    "url": "xxxxxxxxxxxx"
                  }
                },
                "sharingImages": null,
                "mixType": "DAILY_MIX"
              }
            ],
            "dataApiPath": "pages/data/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
          },
          "layout": null
        }
      ]
    }
  ]
}
```