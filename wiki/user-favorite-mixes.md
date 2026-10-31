#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/favorites/mixes?limit=10&locale=en_US&deviceType={enum}&countryCode={country}```
##### Optional Url Parameter
```offset=10``` (Item Offset)\
```order={enum}```\
```orderDirection={enum}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
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
    "items": [
        {
            "dateAdded": "2020-12-21T11:28:56.472365Z",
            "updated": "2020-12-21T05:03:30.683Z",
            "id": "xxxxxxxxxxxxxxxxxxxxx",
            "title": "My Mix 2",
            "mixType": "DAILY_MIX",
            "master": false,
            "images": {
                "SMALL": {
                    "width": 320,
                    "height": 320,
                    "url": "https://images.tidal.com/0/xxxxxxxxx"
                },
                "MEDIUM": {
                    "width": 640,
                    "height": 640,
                    "url": "https://images.tidal.com/0/xxxxxxxxx"
                },
                "LARGE": {
                    "width": 1500,
                    "height": 1500,
                    "url": "https://images.tidal.com/0/xxxxxxxxx"
                }
            },
            "subTitle": "Dave Brubeck, Keith Jarrett, John Coltrane and more",
            "subTitleTextInfo": {
                "text": "Dave Brubeck, Keith Jarrett, John Coltrane and more",
                "color": "#EAD8AB"
            },
            "titleTextInfo": {
                "text": "My Mix 2",
                "color": "#EAD8AB"
            }
        }
    ],
    "cursor": null,
    "lastModifiedAt": "2020-12-21T11:28:56.472365Z"
}
```

#### Update 2026-11 (verified)
* Pagination is cursor based now: the response is `{"items": [...], "cursor": "..."}`. Pass `cursor={cursor}` to get the next page.
* Header ```x-tidal-client-version: {version}``` is needed.
* Only the ids: `GET https://api.tidal.com/v2/favorites/mixes/ids?limit=500&cursor=&countryCode={country}` → `{"content": [...], "cursor": null}`
