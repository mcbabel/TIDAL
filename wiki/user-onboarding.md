### Get Onboarding Steps (verified 2026-11)
* Flags for onboarding hints the user has already seen.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/onboarding?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
[
  {
    "key": "CAST",
    "value": "true"
  },
  {
    "key": "CONTRIBUTOR",
    "value": "true"
  },
  {
    "key": "MENU_OFFLINE_CONTENT",
    "value": "true"
  },
  {
    "key": "ONBOARDING_WELCOME",
    "value": "true"
  },
  ...
]
```

### Set Onboarding Step (from web player code 2026-11, not live-tested)
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/onboarding?countryCode={country}```
##### Url-Encoded POST Parameter
```key: {key}```\
```value: true```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

### Set Early Access Program (from web player code 2026-11, not live-tested)
* Opts the user in or out of TIDAL's early access (beta) program. `GET` answers `405` (verified 2026-11). The current state is `earlyAccessProgram` in [Get User](user).
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/earlyAccessProgram?countryCode={country}```
##### Url-Encoded POST Parameter
```active: true|false```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```
