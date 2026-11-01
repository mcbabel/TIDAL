### Get Search Suggestions (verified 2026-11)
* Suggestions while typing, incl. search history and direct hits.
* Without user: `https://api.tidal.com/v2/client-suggestions/` (same parameters and response, client token).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/suggestions/?query={query}&explicit=true&hybrid=true&countryCode={country}&locale={locale}&deviceType={enum}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "history": [ ... ],
  "suggestions": [
    {
      "query": "the notwist",
      "highlights": []
    },
    {
      "query": "notwo autechre",
      "highlights": [
        {
          "start": 0,
          "length": 4
        }
      ]
    }
  ],
  "directHits": [
    {
      "type": "ARTISTS",
      "value": {
        "id": 3529689,
        "name": "The Notwist",
        ...
      }
    }
  ],
  "suggestionUuid": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
}
```

### Delete Search History Entry (verified 2026-11)
##### Method
```DELETE```
##### Url
```https://api.tidal.com/v2/suggestions/?query={query}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
* Searches with [Search v2](search-v2) are added to `history`. Tested: search for a test term, entry appears in `history` (`{"query": "...", "highlights": []}`), `DELETE` answers `204 No Content`, entry is gone.
