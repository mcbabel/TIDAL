#### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults?filter[query]={query}&countryCode={country}&include={relationships}```
##### Relationships (include)
```topHits```, ```artists```, ```albums```, ```tracks```, ```videos```, ```playlists```
##### Optional Url Parameter
```explicitFilter=INCLUDE``` or ```EXCLUDE```
##### Header
```Authorization: Bearer {access_token}``` (Client Credentials or PKCE, personalized with scope `search.read`)\
```Accept: application/vnd.api+json```
#### Example Response

``` yaml
{
  "data": [
    {
      "id": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
      "type": "searchResults",
      "attributes": {
        "query": "notwist",
        "trackingId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
      },
      "relationships": {
        "topHits": {
          "data": [
            {
              "id": "3529689",
              "type": "artists"
            },
            {
              "id": "499880448",
              "type": "albums"
            }
          ]
        }
      }
    }
  ],
  "links": {
    "self": "/searchResults?filter%5Bquery%5D=notwist&include=topHits&countryCode=DE"
  },
  "included": [ ... ]
}
```
#### Notes
* Older versions of the API used `GET /searchresults/{query}`. The current form is `GET /searchResults?filter[query]={query}`.
* Suggestions while typing: `GET /searchSuggestions?filter[query]={query}`
