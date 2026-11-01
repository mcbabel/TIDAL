Live test of the whole documentation on **2026-11-01** with a real TIDAL account (Premium) in the TIDAL web player (version 2026.10.31). The account owner logged in themselves; all tests ran in that browser session.

#### Rules of the test
* Read requests: everything that could be reached.
* Write requests: only with own test objects (`zz-api-doc-test…`) or with items that were not in the account before, and everything was removed again afterwards. At the end favorites, folders, mixes, blocks, search history and playlists were compared with the state before the test: identical.
* Write requests that cannot be undone, that publish something in the name of the account, that touch money, legal decisions or credentials, or that need a second account or device were **not executed**. Where it was possible without any effect, the endpoint was checked with a non-existent id or an invalid body instead.

#### Private API (api.tidal.com)
| Result | Endpoints |
|---|---|
| ✅ Verified (read) | All catalog, page, search, user, favorites, playlist, mix, feed, pages, v2 home/artist/search/suggestions/folders/profiles, playback info (all qualities), video urls, lyrics, blocks, onboarding, welcome, purchases endpoints |
| ✅ Verified (write with cleanup) | Favorites add/delete (tracks, albums, artists, videos, playlists, mixes), playlist create (v1 + v2) / rename / add / move / replace / delete item / delete, public/private, My Collection folders (create, rename, move, remove), blocks, search history delete, onboarding flag and early access (same value again), feed seen |
| 🔎 Endpoint verified without effect | Cloud queue (connectqueue.tidal.com, fake queue id / invalid body), Widevine license (empty body), checkout (empty body), home task (fake id), AI chat (not enabled for the account) |
| 👀 Observed in the web player traffic | `tidal.com/api/event-batch`, `tidal.com/api/public/event-batch` |
| ✅ Verified with a Widevine capable Google Chrome (remote controlled via DevTools protocol, separate profile) | Widevine service certificate and license (`api.tidal.com/v2/widevine`, key status `usable`), full DRM playback flow, Dolby Atmos manifests (`EAC3_JOC`), one-stream rule: `PRIVILEGED_SESSION_NOTIFICATION` received when a second device started playback |

Not executed in the private API, and why:

| Endpoint | Why not |
|---|---|
| `POST login/username` | Needs the real password of the account; the client ids that allowed it are disabled. |
| `POST logout`, `web-session/logout` | Would log the account owner out of their own browser session. |
| `web-session/credentials`, `session/hydrate` | Only used by the web player when it has no token / in the sign-up redirect; calling it manually means logging in with the session cookie. |
| `POST users/{id}/image` | Replaces the profile picture; there is no way to restore the old one. |
| `POST welcome/users/artists` | Overwrites the taste profile used for recommendations; the old selection cannot be read back. |
| Offline endpoints (`users/{id}/clients/{clientId}/offline/...`) | Need a mobile/desktop client with offline downloads; the account has none. |
| Cloud queue (create a real queue) | There is no endpoint to delete a queue; it could show up on TIDAL Connect devices. |
| Marketplace payouts, Stripe, Cash App, checkout | Move or connect real money and payment accounts. |
| FairPlay | Needs Safari with Apple's FairPlay CDM (macOS/iOS). Not available on the Linux test machine. |
| Facebook, Amazon, handover token | See [Status of legacy endpoints](legacy-status). |

#### Android app (com.aspiro.tidal 2.215.0)
The app was pulled from the test account owner's phone (Play Store install) with `adb`. All 271 private API operations were extracted from its Retrofit interfaces and called against the live API with the same account (Android query parameters `platform=ANDROID`, `deviceType=PHONE`; the requests used the account's session of the web player, because the client id of the app is not used in this documentation).

| Result | Operations |
|---|---|
| ✅ Verified (`2xx`, incl. write tests with cleanup) | 182 |
| ⚠️ Answered with an error documented on the page (e.g. feature disabled for the account, non-existent id, removed endpoint, server error) | 20 |
| 🔎 Endpoint verified without effect (non-existent id / invalid body) | 11 |
| Not executed (reason in the list) | 43 |
| Not reached (no object of this type in the account) | 7 |
| n/a (generic url call without fixed endpoint) | 8 |

All 390 official API operations of the app are part of the official spec and covered by the official API tests below. Details per endpoint: [List of all Android Endpoints](android-endpoints).

Not executed in the Android API, and why (in addition to the web list above):

| Endpoints | Why not |
|---|---|
| `my-collection/playlists/set-public/all` | Would make all private playlists of the account public. |
| `profile/profile-name`, `profile/social-handles`, `profile/onboarded`, `profile/picture` | Change the public profile of the account; the old values (no profile name, no picture) cannot be restored exactly or the change cannot be undone. |
| `users/{id}` (POST: EULA, profile name, account data), `users/{id}/email/verify`, `email-change` | Change personal account data, accept the EULA or send emails. |
| `users/{id}/clients/offline`, offline albums/playlists | Need a device client of an app installation with offline rights; the account had none. |
| `report/offlineplays`, `api/event-batch` (pulsar) | Would add fake plays or events to TIDAL's statistics. |
| `play/autologin`, `registration/play`, `ipt`, `oauth2/*` | Login and token flows: need a signed operator JWT or the app's client id, or issue new login credentials. |
| `upload/terms` (POST), `users/{id}/contentCreatorInfo` (POST), marketplace, Stripe, Cash App | Accept legal terms or connect/move real payment accounts and money. |
| `welcome/users/artists` | Overwrites the taste profile used for recommendations. |
| Experiments / feature flags (`/1.0/…`) | Block's experimentation backend; host is set at runtime and not identified; tracking calls would write analytics data. |

Also found during the Android test:
* `onboarding/list` takes repeated `keys` fields; a comma separated value created one wrong flag during the test, which was removed again (all 22 onboarding flags are identical to before).
* `users/{id}/handovertoken` was called once by the automatic GET run (`200`, token not printed or stored).
* Search suggestions requests added the test search term to the search history; it was deleted again.

#### Official API (openapi.tidal.com/v2), 438 operations
| Result | Operations |
|---|---|
| ✅ Verified (`2xx`) | 266 |
| Answered with a documented error (e.g. `404` for owner/statistics relations that only exist for own uploads, `403` partner only) | 40 |
| 🔎 Endpoint verified with a non-existent id (no effect possible) | 47 |
| Not executed (see below) | 29 |
| Not reached: no object of this type exists for the account | 56 |

Every operation on the [reference pages](official-endpoints) has its own **Live test 2026-11-01** line with the result.

Not executed in the official API, and why:

| Operation | Why not |
|---|---|
| `POST /acceptedTerms` | Accepts TIDAL terms and conditions in the name of the account. That is a legally binding decision of the account owner and cannot be undone. |
| `POST /albums` | Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users. |
| `POST /appreciations` | Sends an appreciation to an artist. The artist sees it, it cannot be taken back. |
| `POST /artistClaims` | Legal ownership claim for an artist profile or content. Claims are reviewed by TIDAL staff; a test claim would be a false claim. |
| `POST /artists` | Creates a public artist profile for the account. |
| `POST /artworks` | Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users. |
| `POST /clientCertificates` | Creates API credentials (client id + secret) or TIDAL Connect partner certificates for the account. |
| `POST /clients` | Creates API credentials (client id + secret) or TIDAL Connect partner certificates for the account. |
| `POST /collaborationInviteRedemptions` | Joins another user's playlist. Needs an invite code from a different account. |
| `POST /comments` | Comments can only be posted on albums, tracks and uploads of other people. They are public and the artist is notified. |
| `POST /contentClaims` | Legal ownership claim for an artist profile or content. Claims are reviewed by TIDAL staff; a test claim would be a false claim. |
| `POST /installations` | Registers a device installation for offline downloads. There is no endpoint to delete an installation again. |
| `POST /lyrics` | Only allowed for the owner of the track (own uploads). The test account owns no tracks. |
| `POST /manualArtistClaims` | Legal ownership claim for an artist profile or content. Claims are reviewed by TIDAL staff; a test claim would be a false claim. |
| `POST /operations` | Atomic operations are only used to create Square shop catalog items (selling merchandise), see Square below. |
| `POST /priceConfigurations` | Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts. |
| `POST /reactions` | Reactions are only possible on public content (albums, tracks, artists, videos, comments), not on private test playlists (verified: `400 Reactions are not supported for subject type: playlists`). On public content they are visible to others. |
| `POST /savedShares` | Saves a share link of another user. Needs a share code from a different account, and there is no endpoint to remove a saved share. |
| `POST /squareConnections` | Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts. |
| `POST /squareItemVariationPhysicalCounts` | Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts. |
| `POST /squareItemVariations` | Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts. |
| `POST /stripeConnections` | Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts. |
| `POST /subscriptionPriceChangeDecisions` | Accepts or declines a price change of the subscription. Billing decision of the account owner. |
| `POST /temporaryUserTokens` | Creates temporary login tokens for the account (new credentials). |
| `POST /trackSourceFiles` | Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users. |
| `POST /tracks` | Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users. |
| `POST /usageRules` | Sets usage rules (stream, DJ, download) for own uploads. Only for content owners; the test account owns no content. |
| `POST /userDataExportRequests` | Starts a GDPR export of all account data (sends emails and builds a data package). |
| `POST /userReports` | Reports content or users to TIDAL moderation. A test report would be a false report. |

Not reached (no object of this type in the account), grouped by resource:

| Resource | Operations | Why |
|---|---|---|
| [artistClaims](official-ref-artistClaims) | 4 | The account has no artist claims (creating one is not done, see `POST /artistClaims`). |
| [artistSalesStatistics](official-ref-artistSalesStatistics) | 2 | The list answered `200` without data: statistics only exist for artist accounts with sales. |
| [artistStreamsStatistics](official-ref-artistStreamsStatistics) | 2 | The list answered `200` without data: statistics only exist for artist accounts. |
| [artworkLibraries](official-ref-artworkLibraries) | 3 | No artwork library exists for the account (`/artworkLibraries/me` answers `404`). |
| [clientCertificates](official-ref-clientCertificates) | 2 | TIDAL Connect partner only (`403 TIDAL Connect partner access is required`). |
| [comments](official-ref-comments) | 4 | The account has no comments (creating one is not done, see `POST /comments`). |
| [contentClaims](official-ref-contentClaims) | 4 | The account has no content claims (creating one is not done, see `POST /contentClaims`). |
| [groups](official-ref-groups) | 1 | The list answered `404`; no group ids are available to the account. |
| [installations](official-ref-installations) | 3 | The account has no installations (the web player does not register one; creating one is not done, see `POST /installations`). |
| [offlineTasks](official-ref-offlineTasks) | 4 | Offline tasks belong to an installation; the account has none. |
| [priceConfigurations](official-ref-priceConfigurations) | 1 | Commerce object; none exists for the account. |
| [providerOwners](official-ref-providerOwners) | 2 | The list answered `200` without data: only for content provider (label) accounts. |
| [providerProductInfos](official-ref-providerProductInfos) | 2 | The list answered `200` without data for the tested provider. |
| [purchases](official-ref-purchases) | 2 | The account has no purchases (the list answered `200` without data). |
| [reactions](official-ref-reactions) | 3 | No reaction could be created for testing (see `POST /reactions`). |
| [squareConnections](official-ref-squareConnections) | 3 | Commerce (Square shop); none exists for the account. |
| [squareItemVariations](official-ref-squareItemVariations) | 3 | Commerce (Square shop); none exists for the account. |
| [squareItems](official-ref-squareItems) | 4 | Commerce (Square shop); terms not accepted (`403 REQUIRED_TERMS_NOT_ACCEPTED`). |
| [squareSites](official-ref-squareSites) | 1 | Commerce (Square shop); none exists for the account. |
| [stripeConnections](official-ref-stripeConnections) | 1 | Commerce (Stripe); none exists for the account. |
| [stripeDashboardLinks](official-ref-stripeDashboardLinks) | 1 | Commerce (Stripe); none exists for the account. |
| [subscriptionPriceChangeDecisions](official-ref-subscriptionPriceChangeDecisions) | 1 | Only exists when TIDAL announced a price change for the subscription; none for the account. |
| [temporaryUserTokens](official-ref-temporaryUserTokens) | 2 | The account has no temporary tokens (creating one is not done, see `POST /temporaryUserTokens`). |
| [userSubscriptionPriceChanges](official-ref-userSubscriptionPriceChanges) | 1 | Only exists when TIDAL announced a price change for the subscription; none for the account. |

#### Also found during the test
* Searches with a user token (private `v2/search` and official `searchResults`) are stored in the account's search history. Delete test searches with [Delete Search History Entry](search-suggestions).
* The API returns the keys of `favorites/ids` in varying order; compare the content, not the text.
* The official `PATCH /playlists/{id}` response can still contain the old attributes; the next `GET` shows the new values.
* AI playlist generation (`POST /playlistGenerations`) takes about 30-60 seconds (`status: PROCESSING` → `OK`). A generation schedule can only be created after the first generation is done (`409` before).
* Track preferences of a generation use optimistic locking: send the current `meta.preferenceVersion` as `meta.expectedPreferenceVersion`, otherwise `409`.
* Full tracks from the official `trackManifests` are Widevine encrypted for every format (also stereo FLAC). The current web player plays through the official API and therefore needs Widevine (`S6001` in browsers without it). The private `playbackinfo` still returns unencrypted streams. See [DRM](drm).
* The built-in browser of the test machine had no Widevine CDM; the DRM tests ran in a separate, remote controlled Google Chrome instance with its own profile, which was deleted afterwards.

#### App OAuth clients (2026-11-01)
To test the login and token flows that the earlier runs could only describe, the OAuth client credentials shipped in the Android app (`assets/secrets.properties`, ~24 client configs) were used. The actual id/secret values are not reproduced in the documentation ([API Keys](Copyright)).

| Flow | Result |
|---|---|
| `client_credentials` (all variants) | ✅ `200`, no-user token, `clientName` identifies the variant |
| Device authorization (TV/FireTV) | ✅ `200`, real `userCode`; phone client rejected (`not a Limited Input Device client`) |
| Device-code token exchange | ✅ `200` after the account owner approved the code on `link.tidal.com` (full login) |
| `refresh_token` | ✅ `200` |
| `update_client` | ✅ `200` (new access + refresh token) |
| `logout` | ✅ `204`, token then `401` |
| Offline authorize (`clients/offline`) with the TV token | ⚠️ `403` — gated by the native app / Play Integrity |

Cleanup: the TV login registered a device/client on the account; all three issued sessions were logged out (`204`, then `401`), and the token files were shredded. The device may still appear as a signed-out "TIDAL TV" entry in the account's device list and can be removed there. Account data (favorites, playlists, …) was not changed. No client id, secret or token value was written to the documentation.

The only login step that could not be scripted here is the **browser** code exchange of the phone PKCE flow (the built-in browser is not allowed to drive the credentialed login page); the PKCE token endpoint itself is the same `oauth2/token` that was verified with the other grants.