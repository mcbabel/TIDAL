### Get Video Credits (verified 2026-11)
* Same format as [Get Track Credits](track-credits).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/credits?includeContributors=true&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
[]
```

### Get Video Recommendations (answered 500)
* Answered `500 "Ooops, an unexpected error occurred"` for the tested video (server error at TIDAL).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/recommendations?limit={limit}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
