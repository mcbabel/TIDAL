#### Example Request
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/favorites/mixes/remove?mixIds={id}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
    "deletedItems": [
        "xxxxxxxxxxxxxxxxxx"
    ],
    "itemsNotRemoved": [],
    "lastModifiedAt": "2020-12-21T11:28:56.472365Z"
}
````

#### Update 2026-11 (verified)
Still works. Add ```onArtifactNotFound=FAIL``` and the header ```x-tidal-client-version: {version}```.
