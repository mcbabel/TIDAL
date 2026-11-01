### Get Privacy / Terms Url (verified 2026-11)
* Terms: `GET v1/url/terms`
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/url/privacy```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "url": "http://tidal.com/privacy"
}
```

### Get Sign Up / Offerings Url (answered 404 for the tested values)
* Url of the sign up / offer page for the mobile operator of the SIM card. Variants: with `networkOperatorName` instead of `simCountryIso`/`simOperator`; offerings: `GET v1/properties/offeringsurl` (additionally `subscriberId`).
* Answered `404 "Sign up URL not found"` / `"Offerings url not found for the given context"` for the tested operator values; it only returns a url for operators that have a TIDAL partnership.
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/properties/signupurl?clientType=ANDROID&simCountryIso={iso}&simOperator={mccmnc}```
##### Header
```authorization: Bearer {access_token}```
