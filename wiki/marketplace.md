### Get Purchases (verified 2026-11)
* Ids of albums and tracks the user bought (TIDAL sells uploads of independent artists).
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/marketplace/v1/user-purchases```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-authenticated-userid: {userId}```
#### Example Response
``` yaml
{
  "albums": [],
  "tracks": []
}
```

### Get Spotlight Seller Status (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/marketplace/spotlight/v1/user```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-authenticated-userid: {userId}```
#### Example Response
``` yaml
{
  "userId": 123456789,
  "payoutTermsAccepted": false,
  "payoutMeansAvailable": false,
  "idvRequirementFulfilled": false,
  "availablePayoutProviders": [ ... ],
  "firstSpotlightedAt": null
}
```

### Checkout (from web player code 2026-11, not live-tested)
* Starts the purchase of an upload (Stripe). Return url: `https://tidal.com/marketplace/checkout/return`.
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/marketplace/v3/checkout```
##### Header
```authorization: Bearer {access_token}```

### Seller Balance / Payouts (from web player code 2026-11, not live-tested)
* Payout: `POST marketplace/v1/sellers/payouts`. Stripe onboarding: `POST https://api.tidal.com/v2/v1/sellers/stripe`, dashboard link: `POST .../v1/sellers/stripe/dashboard`. Payout terms: `POST marketplace/spotlight/v1/user/payout-terms`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/marketplace/v1/sellers/balance```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-authenticated-userid: {userId}```

### Cash App Contributions (from web player code 2026-11, not live-tested)
* Artist tips via Cash App: `POST`/`DELETE marketplace/v1/cashapp/authorize`, `PATCH marketplace/v1/cashapp/contributions?contributionsEnabled=true|false`, `GET marketplace/v1/cashapp/contributions/{id}/links`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/marketplace/v1/cashapp/customer```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-authenticated-userid: {userId}```
