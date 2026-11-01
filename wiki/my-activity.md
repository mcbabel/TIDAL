### Get My Activity Home (verified 2026-11)
* Listening statistics ("My Activity") of the Android app (`com.aspiro.tidal` 2.215.0).
* `currentZonedDateTime`: current local time with offset, e.g. `2026-11-01T02:55:00+01:00` (url encoded).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-activity/home?currentZonedDateTime={dateTime}```
##### Common Url Parameter (added by the Android app)
```countryCode={country}```, ```locale={locale}```, ```deviceType=PHONE```, ```platform=ANDROID```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "activities": [
    {
      "@class": "com.tidal.usercontent.houseofcards.…",
      "images": [ { "id": "DEFAULT", "url": "https://images.tidal.com/1/…" } ],
      "artists": [ { "id": 3529689, "name": "The Notwist", "nrOfStreams": 42 } ],
      "nrOfDaysLeft": 0,
      "activityType": "CURRENT_TOP_STREAMED_ARTIST_DOUBLE",
      "year": 2026,
      "month": 10,
      "title": "…",
      "header": "Your top artists"
    }
  ],
  "educationals": [ { "title": "…", "subtitle": "…", "type": "LEARN_MORE_EDUCATIONAL_ENTRY" } ],
  "updateFrequency": "Updated daily",
  "metadata": { "timeline": [ { "year": 2026, "month": 10, "title": "October ’26" } ] }
}
```

### Get Timeline (verified 2026-11)
* Months for which statistics exist.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-activity/timeline?currentZonedDateTime={dateTime}&locale={locale}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "timeline": [ { "year": 2026, "month": 10, "title": "October ’26" } ]
}
```

### Get Top Artists (verified 2026-11)
* Top artists of a month with the number of streams.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-activity/top-artists?currentZonedDateTime={dateTime}&locale={locale}&month={month}&year={year}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "activity": { "activityType": "CURRENT_TOP_STREAMED_ARTIST_DOUBLE", "year": 2026, "month": 10, "title": "…", "subtitle": "…", … },
  "artists": [
    {
      "artist": { "id": 3529689, "name": "The Notwist", "picture": "…", "popularity": 68, "mixes": { "ARTIST_MIX": "…" }, … },
      "nrOfStreams": 42
    }
  ],
  "metadata": { "timeline": [ … ] },
  "disclaimers": [ { "text": "…", "url": "https://support.tidal.com/…" } ]
}
```

### Get Top Artists Sharing Images (verified 2026-11)
* Share cards (images and texts) for the top artists.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/my-activity/top-artists/share/all?currentZonedDateTime={dateTime}&locale={locale}&month={month}&year={year}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "cards": [ … ],
  "sharingMessages": [ … ]
}
```
