#### Example Request
##### Method
```PUT```
##### Url
```https://api.tidal.com/v2/favorites/mixes/add?countryCode={country}```
##### onArtifactNotFound Enums
```FAIL```\
```SKIP```
##### Url-Encoded PUT Parameter
```mixIds: {id}```\
```onArtifactNotFound: {enum}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
    "addedItems": [
        "xxxxxxxxxxxxxxxxxx"
    ],
    "itemsNotAdded": [],
    "lastModifiedAt": "2020-12-21T11:28:56.472365Z"
}
````

#### Update 2026-11 (verified)
Still works. The parameters can also be sent as Url Parameter: `PUT https://api.tidal.com/v2/favorites/mixes/add?mixIds={id}&onArtifactNotFound=FAIL&countryCode={country}` with header ```x-tidal-client-version: {version}```.
