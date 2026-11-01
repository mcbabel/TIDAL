All private API operations of the TIDAL Android app 2.215.0, extracted from its Retrofit interfaces (see [Android](Android)) and tested on 2026-11-01 with a real Premium account in a live session. The 390 operations of the official API used by the app are in [Official API Endpoints](official-endpoints).

**271 operations:** ✅ verified 182 · ⚠️ answered with an error that is documented here 20 · 🔎 endpoint verified without effect (non-existent id / invalid body) 11 · not executed (with reason) 43 · not reached (no object of this type in the account) 7 · n/a (generic URL call without fixed endpoint) 8

Bases: `/v1/` = `https://api.tidal.com/v1/`, `/v2/` = `https://api.tidal.com/v2/`, `openapi/` = `https://openapi.tidal.com/v2/`, `auth/` = `https://auth.tidal.com/v1/`, `connectqueue/` = `https://connectqueue.tidal.com/v1/`, `sonos/` = `https://sonos.tidal.com/v1/sonos/cloudqueue/`, `pulsar/` = `https://pulsar.tidal.com/`, `experiments/` = experimentation service of Block (host not verified).

Write tests used test objects or items that were not in the account before; everything was removed again and the account state was compared before/after. Reasons for everything not executed are in the table and in the [Test Report](TestReport).

###### (generic url)
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreAlbums` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreAnyMedias` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreArticles` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreArtists` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreContributionItems` | `Url`, `offset`, `limit`, `roleCategoryFilters`, `order`, `orderDirection` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreMixes` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMorePlaylists` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreTracks` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageCollectionService.getMoreVideos` | `Url`, `offset`, `limit` | ✅ 200 | [→](page-home) |
| `GET` | `/v1/{url}` | `DynamicPageService.getPage` | `Url`, `If-None-Match` | ✅ 200 | [→](page-home) |
| `GET` | `/v2/{url}` | `PlayableContentService.getPlayableContent` | `Url`, `offset` | ✅ 200 – needs platform=ANDROID | [→](artist-playable) |
| `GET` | `/v2/{url}` | `AutoHomeService.get` | `Url`, `deviceType` | ✅ 200 – needs platform=ANDROID | [→](home-feed-static) |
| `GET` | `/v1/{url}` | `HomeService.getExternalUrl` | `Url` | n/a – generic URL fetch (no fixed endpoint) |  |
| `GET` | `/v2/{url}` | `ViewAllService.get` | `Url`, `refreshId`, `timeOffset`, `offset`, `limit` | ✅ 200 – needs platform=ANDROID | [→](home-feed-vibe) |
| `GET` | `/v1/{url}` | `TicketmasterService.getEvents` | `Url` | n/a – generic URL fetch (no fixed endpoint) |  |
| `GET` | `/v2/onboarding/{url}` | `SetupGuideService.getExternalUrl` | `Url` | n/a – generic URL fetch (no fixed endpoint) |  |
| `GET` | `/v1/{url}` | `a.a` | `Url` | n/a – generic URL fetch (no fixed endpoint) |  |
| `GET` | `/v1/{url}` | `p.a` | `Url` | n/a – generic URL fetch (no fixed endpoint) |  |
| `POST` | `/v1/{url}` | `DrmLicenseService.getWidevineLicense` | `Url`, `Body` | ✅ 200 – manifest licenseUrl, see DRM |  |
| `POST` | `/v1/{url}` | `DrmService$DrmRestClient.getWidevineLicense` | `Url`, `Body` | ⚠️ 500 – legacy url; real licenses go to the manifest licenseUrl |  |
| `POST` | `/v1/{url}` | `a.a` | `Url`, `Body` | n/a – generic URL call |  |
| `POST` | `/v1/{url}` | `a.b` | `Url` | n/a – generic URL call |  |
| `POST` | `/v1/{url}` | `p.a` | `Url`, `Body` | n/a – generic URL call |  |

###### 1.0
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `experiments//1.0/experimentation/activate-experiment` | `AnalyticsService.trackActivation` | `Body` | not executed – experiment analytics | [→](experiments) |
| `POST` | `experiments//1.0/experimentation/get-experiments` | `LatestExperimentsService.getLatestExperiments` | `Body` | not executed – experimentation backend of Block, host and auth not reachable | [→](experiments) |
| `POST` | `experiments//1.0/experimentation/record-exclusion` | `AnalyticsService.trackExclusion` | `Body` | not executed – experiment analytics | [→](experiments) |
| `POST` | `experiments//1.0/experimentation/track-event` | `AnalyticsService.trackEvent` | `Body` | not executed – experiment analytics | [→](experiments) |
| `POST` | `experiments//1.0/features/get-flags` | `FeatureFlagsService.getFeatureFlags` | `Body` | not executed – feature flag backend of Block, host and auth not reachable | [→](experiments) |

###### albums
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/albums/{id}` | `AlbumService.getAlbum` | `id` | ✅ 200 |  |
| `GET` | `openapi/albums/{id}` | `TopAlbumsService.getAlbumWithPriceConfig` | `id`, `countryCode`, `include` | ✅ 200 |  |
| `GET` | `/v1/albums/{id}/credits` | `AlbumService.getCredits` | `id`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/albums/{id}/items` | `AlbumService.getItems` | `id`, `replace`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/albums/{id}/items/credits` | `AlbumService.getItemsWithCredits` | `id`, `replace`, `offset`, `limit`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/albums/{id}/review` | `AlbumService.getReview` | `id` | ✅ 200 |  |

###### api
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `pulsar/api/event-batch` | `SqsService.sendEventsBatch` | `FieldMap` | not executed – would send fake events; observed in the web player | [→](event-batch) |
| `POST` | `pulsar/api/public/event-batch` | `SqsService.sendEventsBatchPublic` | `FieldMap` | not executed | [→](event-batch) |

###### artist
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/artist/{id}` | `ArtistResonanceService.getArtist` | `id` | ✅ 200 – needs platform=ANDROID | [→](home-feed-vibe) |

###### artists
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/artists/{id}` | `ArtistService.getArtist` | `id` | ✅ 200 |  |
| `GET` | `/v1/artists/{id}` | `ArtistService.getArtistSingle` | `id` | ✅ 200 |  |
| `GET` | `/v1/artists/{id}/bio` | `ArtistService.getBio` | `id` | ✅ 200 |  |
| `GET` | `/v1/artists/{id}/mix` | `ArtistService.getMixId` | `id` | ✅ 200 |  |
| `GET` | `/v1/artists/{id}/toptracks` | `ArtistService.getTopTracks` | `id`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/artists/{id}/videos` | `ArtistService.getVideos` | `id`, `offset`, `limit` | ✅ 200 |  |

###### broadcasts
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/broadcasts/{djSessionId}/playbackinfo` | `PlaybackInfoService.getBroadcastPlaybackInfo` | `djSessionId`, `audioquality` | ⚠️ 404 – No content available for the requested product. (non-existent DJ session) | [→](broadcast-playbackinfo) |

###### chat
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v2/chat/` | `ChatService.sendMessage` | `Body` | not reached – needs an AI chat session | [→](music-assistant) |
| `POST` | `/v2/chat/init` | `ChatService.init` | `Body` | ⚠️ 400 – "User not enabled for AI chat experiment" | [→](music-assistant) |

###### cloud queue
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `connectqueue/./` | `CloudQueueService.getApiInfo` | – | ✅ 200 | [→](cloud-queue) |

###### content
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `connectqueue/content/{queueId}` | `CloudQueueService.getQueueContent` | `queueId`, `offset`, `limit` | ⚠️ 404 – queue_not_found (non-existent queue id) | [→](cloud-queue) |

###### drm
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/drm/licenses/widevine` | `DrmService$DrmRestClient.getWidevineLicense` | `Body` | ⚠️ 500 – legacy url; real licenses go to the manifest licenseUrl | [→](drm) |

###### email-change
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v2/email-change` | `EmailChangeService.startEmailChange` | – | not executed – starts an email change and sends emails | [→](user-account) |
| `POST` | `/v2/email-change/{id}/resend` | `EmailChangeService.resendEmailChange` | `id` | 🔎 404 – non-existent id | [→](user-account) |

###### feed
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/feed/activities` | `FeedService.getFeed` | `userId`, `limit` | ✅ 200 | [→](feed-activities) |
| `PUT` | `/v1/feed/activities/seen` | `FeedService.reportFeedSeen` | `userId` | ✅ 200 | [→](feed-activities) |
| `GET` | `/v2/feed/activities/unseen/exists` | `FeedService.hasUnseenFeed` | `userId` | ✅ 200 | [→](feed-activities) |

###### follow
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `DELETE` | `/v2/follow/` | `ProfileService.unfollowUser` | `trn` | ✅ 200 | [→](profiles) |
| `DELETE` | `/v2/follow/` | `ProfilesService.unfollowUser` | `trn` | ✅ 200 | [→](profiles) |
| `PUT` | `/v2/follow/` | `ProfileService.followUser` | `trn` | ✅ 200 – artist trn, unfollowed again | [→](profiles) |
| `PUT` | `/v2/follow/` | `ProfilesService.followUser` | `trn` | ✅ 200 – artist trn | [→](profiles) |

###### googleplay
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/googleplay/purchase/status` | `ProductPickerService.getSubscriptionStatus` | `purchaseToken`, `productId` | ✅ 200 | [→](android-billing) |
| `GET` | `/v1/googleplay/subscriptions/active` | `ProductPickerService.getSubscriptions` | – | ✅ 200 | [→](android-billing) |

###### home
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/home/feed/{vibe}` | `AutoHomeService.getHomePageResonance` | `vibe`, `cursor`, `timeOffset`, `limit`, `deviceType` | ✅ 200 – needs platform=ANDROID | [→](home-feed-vibe) |
| `GET` | `/v2/home/feed/{vibe}` | `HomeService.getHomePageResonance` | `vibe`, `refreshId`, `cursor`, `timeOffset`, `limit` | ✅ 200 – needs platform=ANDROID | [→](home-feed-vibe) |

###### ipt
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `auth/ipt` | `OneTimeTokenService.getOneTimeToken` | – | not executed – issues a one-time login token | [→](Android) |

###### items
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `sonos/items/{groupId}` | `CloudQueueService$CloudQueueRestClient.uploadItemList` | `groupId`, `Body` | 🔎 400 – Sonos host, validation error without data; needs a Sonos group | [→](cloud-queue) |

###### logout
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/logout` | `LogoutService$LogoutRestClient.logout` | – | not executed – would log the account out |  |

###### marketplace
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/marketplace/spotlight/v1/user` | `SpotlightService.getUser` | – | ✅ 200 | [→](marketplace) |
| `POST` | `/v2/marketplace/spotlight/v1/user/payout-terms` | `SpotlightService.acceptTerms` | – | not executed – accepts payout terms | [→](marketplace) |
| `DELETE` | `/v2/marketplace/v1/cashapp/authorize` | `CashAppService.unlinkCashApp` | – | not executed – payment account | [→](marketplace) |
| `POST` | `/v2/marketplace/v1/cashapp/authorize` | `CashAppService.startAuthorization` | `Body` | not executed – payment account | [→](marketplace) |
| `PATCH` | `/v2/marketplace/v1/cashapp/contributions` | `CashAppService.setContributionsEnabled` | `contributionsEnabled` | not executed – payment setting | [→](marketplace) |
| `GET` | `/v2/marketplace/v1/cashapp/customer` | `CashAppService.getCashAppCustomer` | `grantRequestId` | ✅ 200 | [→](marketplace) |
| `GET` | `/v2/marketplace/v1/user-purchases` | `PurchasesService.getUserPurchaseIds` | – | ✅ 200 | [→](marketplace) |
| `POST` | `/v2/marketplace/v3/checkout` | `PurchasesService.createCheckout` | `Body` | 🔎 400 – empty body, no purchase | [→](marketplace) |

###### mixes
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/mixes/{mixId}/items` | `MixService.getItems` | `mixId` | ✅ 200 |  |
| `GET` | `/v1/mixes/{mixId}/items` | `MixService.getTracks` | `mixId` | ✅ 200 |  |
| `GET` | `/v1/mixes/{mixId}/metadata` | `MixService.getMixMetadata` | `mixId` | ✅ 200 | [→](mix-metadata) |

###### my-activity
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/my-activity/home` | `ActivityService.getHomeActivities` | `currentZonedDateTime` | ✅ 200 | [→](my-activity) |
| `GET` | `/v2/my-activity/timeline` | `ActivityService.getTimeline` | `currentZonedDateTime`, `locale` | ✅ 200 | [→](my-activity) |
| `GET` | `/v2/my-activity/top-artists` | `ActivityService.getTopArtists` | `currentZonedDateTime`, `locale`, `month`, `year` | ✅ 200 | [→](my-activity) |
| `GET` | `/v2/my-activity/top-artists/share/all` | `ActivityService.getTopArtistsSharingImages` | `currentZonedDateTime`, `locale`, `month`, `year` | ✅ 200 | [→](my-activity) |

###### my-collection
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `PUT` | `/v2/my-collection/albums/add-favorite` | `MyCollectionAlbumService.addToFavorite` | `id` | ✅ 200 – write test, removed again | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/albums/folders` | `MyCollectionAlbumService.getFoldersAndAlbums` | `cursor`, `folderId`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/albums/remove` | `MyCollectionAlbumService.removeFromFavorite` | `trns` | ✅ 204 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/artists/add-favorite` | `MyCollectionArtistService.addToFavorite` | `artistId` | ✅ 200 – write test, removed again | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/artists/create-folder` | `MyCollectionArtistService.createFolder` | `name` | ⚠️ 404 bad_input – artist folders not available for the test account | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/artists/folders` | `MyCollectionArtistService.getFolderArtists` | `folderId`, `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/artists/folders` | `MyCollectionArtistService.getFolders` | `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/artists/folders` | `MyCollectionArtistService.getFoldersAndArtists` | `cursor`, `folderId`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/artists/remove` | `MyCollectionArtistService.deleteFolder` | `trns` | ✅ 204 – same endpoint as remove | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/artists/remove` | `MyCollectionArtistService.removeFromFavorite` | `trns` | ✅ 204 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/artists/rename` | `MyCollectionArtistService.renameFolder` | `trn`, `name`, `returning` | not reached – needs an artist folder (could not be created) | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/mixes/add-favorite` | `MyCollectionMixService.addToFavorite` | `id` | ✅ 200 – write test, removed again | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/mixes/folders` | `MyCollectionMixService.getFoldersAndMixes` | `cursor`, `folderId`, `limit`, `includeOnly`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/mixes/remove` | `MyCollectionMixService.removeFromFavorite` | `trns` | ✅ 204 | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/playlists/folders` | `MyCollectionPlaylistService.getFolderItems` | `cursor`, `folderId`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-folders) |
| `GET` | `/v2/my-collection/playlists/folders` | `MyCollectionPlaylistService.getFolderPlaylists` | `folderId`, `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-folders) |
| `GET` | `/v2/my-collection/playlists/folders` | `MyCollectionPlaylistService.getFolders` | `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/folders/add-favorite` | `MyCollectionPlaylistService.addToFavorite` | `uuid` | ✅ 200 – write test, removed again | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/playlists/folders/create-folder` | `MyCollectionPlaylistService.createFolder` | `name`, `trns` | ✅ 200 – with `trns`, removed again | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/folders/create-playlist` | `MyCollectionPlaylistService.createNewPlaylist` | `name`, `description`, `folderId`, `isPublic` | ✅ 200 – test playlist, deleted again | [→](my-collection-folders) |
| `GET` | `/v2/my-collection/playlists/folders/flattened` | `MyCollectionPlaylistService.getUserPlaylists` | `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-folders) |
| `GET` | `/v2/my-collection/playlists/folders/flattened` | `ProfileService.getUserPlaylists` | `cursor`, `includeOnly`, `limit`, `order`, `orderDirection` | ✅ 200 | [→](my-collection-folders) |
| `GET` | `/v2/my-collection/playlists/folders/items` | `MyCollectionPlaylistService.getFavoriteOrUserPlaylist` | `trns` | ✅ 200 | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/playlists/folders/items` | `MyCollectionPlaylistService.getUserPlaylist` | `trns` | ✅ 200 | [→](my-collection-v2) |
| `GET` | `/v2/my-collection/playlists/folders/metadata` | `MyCollectionPlaylistService.getPlaylistsMetaData` | `trns` | ✅ 200 | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/playlists/folders/move` | `MyCollectionPlaylistService.movePlaylistsToFolder` | `folderId`, `trns` | ✅ 204 – web test | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/folders/remove` | `MyCollectionPlaylistService.delete` | `trns` | ✅ 204 | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/folders/rename` | `MyCollectionPlaylistService.renameFolder` | `trn`, `name` | ✅ 204 – web test | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/folders/rename` | `MyCollectionPlaylistService.renamePlaylist` | `trn`, `name`, `description` | ✅ 204 – with description | [→](my-collection-folders) |
| `PUT` | `/v2/my-collection/playlists/generate-playlist` | `MyCollectionPlaylistService.createAIPlaylist` | `name`, `folderId`, `isPublic` | ⚠️ 401 – "AI playlist creation disabled" for the test account | [→](my-collection-v2) |
| `PUT` | `/v2/my-collection/playlists/set-public/all` | `MyCollectionPlaylistService.publishAllPlaylistsExcept` | `Body` | not executed – would make all private playlists of the account public | [→](my-collection-v2) |

###### oauth2
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `auth/oauth2/device_authorization` | `LoginService.getDeviceAuthorization` | `client_id`, `scope` | not executed – needs the app client id | [→](Android) |
| `POST` | `auth/oauth2/token` | `TokenService.exchangeSessionIdWithToken` | `user_id`, `session_id`, `client_unique_key`, `client_id`, `scope`, `grant_type` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `TokenService.exchangeUserAuthTokenWithToken` | `user_auth_token`, `client_id`, `client_secret`, `scope`, `client_version`, `client_unique_key`, `grant_type` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `LoginService.getTokenFromDeviceCode` | `client_id`, `client_secret`, `device_code`, `grant_type`, `scope`, `client_unique_key` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `LoginService.getTokenWithCodeVerifier` | `code`, `client_id`, `grant_type`, `redirect_uri`, `scope`, `code_verifier`, `client_unique_key` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `TokenService.getTokenFromClientSecret` | `client_id`, `client_secret`, `grant_type`, `scope` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `TokenService.getTokenFromRefreshToken` | `client_id`, `client_secret`, `refresh_token`, `grant_type`, `scope` | not executed | [→](Android) |
| `POST` | `auth/oauth2/token` | `TokenService.upgradeToken` | `refresh_token`, `client_unique_key`, `client_id`, `client_secret`, `scope`, `grant_type` | not executed | [→](Android) |

###### offline
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/offline/albums` | `OfflineService.getOfflineAlbums` | – | ✅ 200 | [→](android-offline) |

###### onboarding
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/onboarding/tmm/migration` | `OnboardingService.getTmmMigrationUrl` | – | ✅ 200 | [→](onboarding-v2) |

###### pages
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/pages/album` | `DynamicPageService.getAlbumPage` | `albumId`, `If-None-Match` | ✅ 200 |  |
| `GET` | `/v1/pages/artist` | `DynamicPageService.getArtistPage` | `artistId`, `If-None-Match` | ✅ 200 |  |
| `GET` | `/v1/pages/home` | `DynamicPageService.getFrontPage` | `If-None-Match` | ✅ 200 |  |
| `GET` | `/v1/pages/mix` | `DynamicPageService.getMixPage` | `mixId`, `If-None-Match` | ✅ 200 |  |
| `GET` | `/v1/pages/{pageID}` | `DynamicPageService.getPageForID` | `pageID`, `If-None-Match` | ✅ 200 |  |

###### play
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/play/autologin` | `PlayService.getLoginToken` | `loginJwt`, `token` | not executed – operator login with a signed JWT | [→](android-billing) |
| `GET` | `/v1/play/subscriberid` | `PlayService.getSubscriberId` | – | ✅ 204 | [→](android-billing) |

###### playintegrity
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `auth/playintegrity/nonce` | `PlayIntegrityService.getNonce` | – | ✅ 200 | [→](Android) |

###### playlists
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `PUT` | `/v2/playlists/set-public` | `PlaylistServiceV2.publishPlaylists` | `playlistUuids` | ✅ 200 – test playlist | [→](playlist-v2-extras) |
| `PUT` | `/v2/playlists/set-public` | `ProfileService.publishPlaylists` | `playlistUuids` | ✅ 200 – test playlist | [→](playlist-v2-extras) |
| `GET` | `/v2/playlists/{playlistUuid}/status` | `PlaylistServiceV2.pollPlaylistStatus` | `playlistUuid` | ✅ 200 | [→](playlist-v2-extras) |
| `GET` | `/v1/playlists/{uuid}` | `PlaylistService.getPlaylist` | `uuid` | ✅ 200 |  |
| `GET` | `/v1/playlists/{uuid}` | `PlaylistServiceV1.getPlaylistPrivacyState` | `uuid` | ✅ 200 |  |
| `PUT` | `/v2/playlists/{uuid}/images/add` | `PlaylistServiceV2.setPlaylistImage` | `uuid`, `imageId`, `userId` | 🔎 404 bad_input – non-existent image id; needs an uploaded image | [→](playlist-v2-extras) |
| `PUT` | `/v2/playlists/{uuid}/images/remove` | `PlaylistServiceV2.removePlaylistImage` | `uuid`, `userId` | 🔎 404 bad_input – test playlist without image | [→](playlist-v2-extras) |
| `GET` | `/v1/playlists/{uuid}/items` | `PlaylistService.getPlaylistItems` | `uuid`, `order`, `orderDirection`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/playlists/{uuid}/items` | `PlaylistService.getPlaylistItemsSingle` | `uuid`, `order`, `orderDirection`, `offset`, `limit` | ✅ 200 |  |
| `POST` | `/v1/playlists/{uuid}/items` | `PlaylistService.addPlaylistMediaItems` | `uuid`, `fromPlaylistUuid`, `itemIds`, `toIndex`, `onArtifactNotFound`, `If-None-Match` | ✅ 200 – `trackIds` and `fromPlaylistUuid` |  |
| `POST` | `/v1/playlists/{uuid}/items/{index}/replace` | `PlaylistService.replacePlaylistItem` | `uuid`, `index`, `itemId`, `If-None-Match` | ✅ 200 |  |
| `DELETE` | `/v1/playlists/{uuid}/items/{indices}` | `PlaylistService.deletePlaylistMediaItems` | `uuid`, `indices`, `order`, `orderDirection`, `If-None-Match` | ✅ 200 |  |
| `POST` | `/v1/playlists/{uuid}/items/{indices}` | `PlaylistService.movePlaylistMediaItems` | `uuid`, `indices`, `toIndex`, `If-None-Match` | ✅ 200 |  |
| `GET` | `/v1/playlists/{uuid}/recommendations/items` | `PlaylistService.getPlaylistSuggestions` | `uuid`, `offset`, `limit` | ✅ 200 |  |
| `PUT` | `/v2/playlists/{uuid}/set-private` | `PlaylistServiceV2.setPlaylistPrivate` | `uuid` | ✅ 200 | [→](playlist-v2-extras) |
| `PUT` | `/v2/playlists/{uuid}/set-private` | `ProfileService.setPlaylistPrivate` | `uuid` | ✅ 200 | [→](playlist-v2-extras) |
| `PUT` | `/v2/playlists/{uuid}/set-public` | `PlaylistServiceV2.setPlaylistPublic` | `uuid` | ✅ 200 – test playlist | [→](playlist-v2-extras) |

###### profile
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `DELETE` | `/v2/profile/onboarded` | `ProfileService.deboard` | – | not executed – changes the public profile | [→](profiles) |
| `PUT` | `/v2/profile/onboarded` | `ProfileService.onboard` | – | not executed – changes the public profile | [→](profiles) |
| `DELETE` | `/v2/profile/picture` | `ProfileService.deleteProfilePicture` | – | not executed – cannot be undone | [→](profiles) |
| `GET` | `/v2/profile/picture/status` | `ProfileService.pollUserProfilePicture` | – | ⚠️ 404 – no profile picture upload in progress | [→](profiles) |
| `PUT` | `/v2/profile/profile-name` | `ProfilesService.updateProfileName` | `profileName` | not executed – public profile; the account has no profile name to restore | [→](profiles) |
| `PUT` | `/v2/profile/social-handles` | `ProfileService.submitSocialHandles` | `facebook`, `instagram`, `snapchat`, `tiktok`, `twitter`, `userId` | not executed – public profile data | [→](profiles) |
| `GET` | `/v1/profile/{handle}` | `DynamicPageServiceV2.getProfilePage` | `handle`, `If-None-Match` | ⚠️ 404 – Resource not found | [→](profiles) |

###### profiles
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/profiles/followers` | `ProfilesService.getPlaylistFollowers` | `trn`, `cursor` | ✅ 200 | [→](profiles) |
| `GET` | `/v2/profiles/me` | `ProfilesService.getMyProfile` | – | ✅ 200 | [→](profiles) |
| `GET` | `/v2/profiles/{userId}` | `ProfilesService.getProfile` | `userId` | ✅ 200 | [→](profiles) |
| `GET` | `/v2/profiles/{userId}` | `ProfileService.getUserProfile` | `userId` | ✅ 200 | [→](profiles) |
| `GET` | `/v2/profiles/{userId}/followers` | `ProfilesService.getFollowers` | `userId`, `cursor` | ✅ 200 | [→](profiles) |
| `GET` | `/v2/profiles/{userId}/following` | `ProfilesService.getFollowing` | `userId`, `includeOnly`, `cursor` | ✅ 200 | [→](profiles) |

###### properties
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/properties/offeringsurl` | `OfferingsPropertiesService.getOfferingsUrl` | `clientType`, `networkOperatorName` | ⚠️ 404 – Offerings url not found for the given context (needs mobile operator values) | [→](app-urls) |
| `GET` | `/v1/properties/offeringsurl` | `OfferingsPropertiesService.getOfferingsUrl` | `clientType`, `simCountryIso`, `simOperator`, `subscriberId` | ⚠️ 404 – Offerings url not found for the given context (needs mobile operator values) | [→](app-urls) |
| `GET` | `/v1/properties/signupurl` | `SignUpPropertiesService.getSignUpUrl` | `clientType`, `networkOperatorName` | ⚠️ 404 – Sign up URL not found (needs mobile operator values) | [→](app-urls) |
| `GET` | `/v1/properties/signupurl` | `SignUpPropertiesService.getSignUpUrl` | `clientType`, `simCountryIso`, `simOperator` | ⚠️ 404 – Sign up URL not found (needs mobile operator values) | [→](app-urls) |

###### queues
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `connectqueue/queues` | `CloudQueueService.createQueue` | `Body` | 🔎 400 – invalid body; a real queue cannot be deleted | [→](cloud-queue) |
| `GET` | `connectqueue/queues/{queueId}` | `CloudQueueService.getQueue` | `queueId` | ⚠️ 404 – queue_not_found (non-existent queue id) | [→](cloud-queue) |
| `GET` | `connectqueue/queues/{queueId}/items` | `CloudQueueService.getQueueItems` | `queueId`, `offset`, `limit` | ⚠️ 404 – queue_not_found (non-existent queue id) | [→](cloud-queue) |
| `PATCH` | `connectqueue/queues/{queueId}/items` | `CloudQueueService.moveItems` | `queueId`, `Body`, `if-match` | 🔎 400 | [→](cloud-queue) |
| `PUT` | `connectqueue/queues/{queueId}/items` | `CloudQueueService.addQueueItems` | `queueId`, `Body`, `if-match` | 🔎 400 | [→](cloud-queue) |
| `DELETE` | `connectqueue/queues/{queueId}/items/{itemId}` | `CloudQueueService.deleteItem` | `queueId`, `itemId`, `if-match` | 🔎 204 – non-existent queue | [→](cloud-queue) |

###### registration
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/registration/play` | `PlayService.registerWithPlay` | `registrationJwt`, `clientVersion`, `token` | not executed – operator registration with a signed JWT | [→](android-billing) |

###### report
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/report/offlineplays` | `ReportService.reportOfflinePlays` | `Body` | not executed – would add fake plays to the statistics | [→](android-offline) |

###### rt
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v1/rt/connect` | `StreamingPrivilegesService.getStreamingPrivilegesWebSocketUrl` | `sessionId` | ✅ 200 | [→](streaming-privileges) |
| `POST` | `/v1/rt/connect` | `StreamingPrivilegesService.getStreamingPrivilegesWebSocketInfo` | – | ✅ 200 | [→](streaming-privileges) |

###### search
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/search` | `SearchService.getSearch` | `query`, `types`, `offset`, `limit`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/search` | `SearchService.getSearch` | `limit`, `offset`, `query`, `types`, `includeUserPlaylists`, `includeDidYouMean` | ✅ 200 |  |
| `GET` | `/v1/search` | `SearchService$SearchRestClient.getSearch` | `query`, `types`, `offset`, `limit`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/search/albums` | `SearchService$SearchRestClient.getAlbums` | `query`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/search/artists` | `SearchService$SearchRestClient.getArtists` | `query`, `offset`, `limit`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/search/playlists` | `SearchService$SearchRestClient.getPlaylists` | `query`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/search/top-hits` | `SearchService$SearchRestClient.getTopHits` | `query`, `offset`, `limit`, `types` | ✅ 200 | [→](search-top-hits) |
| `GET` | `/v1/search/tracks` | `SearchService$SearchRestClient.getTracks` | `query`, `offset`, `limit` | ✅ 200 |  |
| `GET` | `/v1/search/videos` | `SearchService$SearchRestClient.getVideos` | `query`, `offset`, `limit` | ✅ 200 |  |

###### sessions
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/sessions` | `SessionService.getSessionFromToken` | `Authorization` | ✅ 200 | [→](sessions) |
| `GET` | `/v1/sessions/{sessionId}` | `SessionService.getSession` | `sessionId` | ✅ 200 | [→](sessions) |

###### stripeConnections
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `openapi/stripeConnections` | `StripeConnectionsService.getStripeConnections` | `filter[owners.id]` | ✅ 200 | [→](official-ref-stripeConnections) |
| `POST` | `openapi/stripeConnections` | `StripeConnectionsService.createStripeConnection` | `countryCode`, `Body` | not executed – payment account | [→](official-ref-stripeConnections) |

###### suggestions
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `DELETE` | `/v1/suggestions` | `SearchService.deleteSearchSuggestion` | `query` | ✅ 204 | [→](search-suggestions) |
| `DELETE` | `/v1/suggestions` | `SearchService.deleteSearchSuggestionHistory` | `query` | ✅ 204 | [→](search-suggestions) |
| `GET` | `/v2/suggestions` | `SearchService.getSearchSuggestions` | `query`, `explicit`, `hybrid` | ✅ 200 | [→](search-suggestions) |
| `GET` | `/v2/suggestions` | `SearchService.getSearchSuggestions` | `query`, `hybrid` | ✅ 200 | [→](search-suggestions) |

###### tasks
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/onboarding/tasks` | `SetupGuideService.getSetupTasks` | `locale`, `version` | ✅ 200 | [→](setup-guide) |
| `POST` | `/v2/onboarding/tasks/set-completed/{taskId}` | `SetupGuideService.setTaskCompleted` | `taskId` | 🔎 200 – non-existent task id | [→](setup-guide) |
| `GET` | `/v2/onboarding/tasks/{taskId}` | `SetupGuideService.getSubtasks` | `taskId`, `locale`, `version` | ✅ 200 | [→](setup-guide) |

###### tools
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `POST` | `/v2/tools/master/{itemId}` | `ArtistToolsService.master` | `itemId` | 🔎 404 – non-existent item id | [→](upload-creator) |

###### tracks
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/tracks/{id}` | `TrackService$TrackRestClient.getTrack` | `id` | ✅ 200 |  |
| `GET` | `/v1/tracks/{id}` | `TrackService$TrackRestClient.getTrack` | `id`, `countryCode` | ✅ 200 |  |
| `GET` | `/v1/tracks/{id}/credits` | `CreditsService.getTrackCredits` | `id`, `includeContributors` | ✅ 200 |  |
| `GET` | `/v1/tracks/{id}/mix` | `TrackService$TrackRestClient.getMixId` | `id` | ✅ 200 |  |
| `GET` | `/v1/tracks/{id}/recommendations` | `TrackService$TrackRestClient.getRecommendations` | `id`, `limit` | ✅ 200 |  |
| `GET` | `/v1/tracks/{trackId}/lyrics` | `TrackService$TrackRestClient.getLyrics` | `trackId` | ✅ 200 |  |

###### upload
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/upload/terms` | `TermsService.getTerms` | – | ✅ 200 | [→](upload-creator) |
| `POST` | `/v2/upload/terms` | `TermsService.acceptTerms` | – | not executed – accepts upload terms | [→](upload-creator) |

###### url
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/url/privacy` | `UrlService.getPrivacyUrl` | – | ✅ 200 | [→](app-urls) |
| `GET` | `/v1/url/terms` | `UrlService.getTermsUrl` | – | ✅ 200 | [→](app-urls) |

###### user-playlists
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v2/user-playlists/{userId}/public` | `ProfileService.getPublicPlaylists` | `userId`, `cursor`, `limit` | ✅ 200 |  |
| `GET` | `/v2/user-playlists/{userId}/public` | `PublicPlaylistsService.getPublicPlaylists` | `userId`, `cursor`, `limit` | ✅ 200 |  |
| `GET` | `/v2/user-playlists/{uuid}` | `PlaylistServiceV2.getEnrichedPlaylist` | `uuid` | ✅ 200 – 404 for private playlists | [→](playlist-v2-extras) |

###### users
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/users/{userId}` | `UserService.getUser` | `userId` | ✅ 200 | [→](user-account) |
| `POST` | `/v1/users/{userId}` | `UserService.updateEula` | `userId`, `acceptedEULA` | not executed – accepts the EULA | [→](user-account) |
| `POST` | `/v1/users/{userId}` | `UserService.updateProfileName` | `userId`, `profileName` | not executed – account data | [→](user-account) |
| `POST` | `/v1/users/{userId}` | `UserService.updateUser` | `userId`, `firstName`, `lastName`, `profileName`, `email`, `newsletter`, `gender`, `dateOfBirth` | not executed – account data incl. email | [→](user-account) |
| `GET` | `/v1/users/{userId}/activity` | `RemoteUserActivityRepository$UserActivityRestClient.getUserActivities` | `userId`, `offset`, `limit` | ✅ 200 | [→](user-activity) |
| `GET` | `/v1/users/{userId}/blocks/artists` | `BlockService.getBlockedArtists` | `userId`, `offset`, `limit` | ✅ 200 | [→](user-blocks) |
| `POST` | `/v1/users/{userId}/blocks/artists` | `BlockService.blockArtist` | `userId`, `artistId` | ✅ 200 | [→](user-blocks) |
| `DELETE` | `/v1/users/{userId}/blocks/artists/{artistId}` | `BlockService.unblockArtist` | `userId`, `artistId` | ✅ 204 | [→](user-blocks) |
| `GET` | `/v1/users/{userId}/blocks/ids` | `BlockService.getRecentlyBlockedItems` | `userId` | ✅ 200 | [→](user-blocks) |
| `GET` | `/v1/users/{userId}/blocks/tracks` | `BlockService.getBlockedTracks` | `userId`, `offset`, `limit` | ✅ 200 | [→](user-blocks) |
| `POST` | `/v1/users/{userId}/blocks/tracks` | `BlockService.blockTrack` | `userId`, `trackId` | ✅ 200 | [→](user-blocks) |
| `DELETE` | `/v1/users/{userId}/blocks/tracks/{trackId}` | `BlockService.unblockTrack` | `userId`, `trackId` | ✅ 204 | [→](user-blocks) |
| `GET` | `/v1/users/{userId}/blocks/videos` | `BlockService.getBlockedVideos` | `userId`, `offset`, `limit` | ✅ 200 | [→](user-blocks) |
| `POST` | `/v1/users/{userId}/blocks/videos` | `BlockService.blockVideo` | `userId`, `videoId` | ✅ 200 | [→](user-blocks) |
| `DELETE` | `/v1/users/{userId}/blocks/videos/{videoId}` | `BlockService.unblockVideo` | `userId`, `videoId` | ✅ 204 | [→](user-blocks) |
| `GET` | `/v1/users/{userId}/clients` | `UserService$UserRestClient.getClients` | `userId`, `filter`, `limit` | ✅ 200 |  |
| `POST` | `/v1/users/{userId}/clients/offline` | `ClientService.authorizeClient` | `userId`, `clientId`, `name` | not executed – needs a device client (app installation) | [→](android-offline) |
| `DELETE` | `/v1/users/{userId}/clients/offline/{clientId}` | `ClientService.deauthorizeClient` | `userId`, `clientId` | not executed – needs an authorized device | [→](android-offline) |
| `GET` | `/v1/users/{userId}/clients/{clientId}/offline/albums` | `UserService$UserRestClient.getOfflineAlbums` | `userId`, `clientId`, `limit` | ⚠️ 400 – Bad request (no offline client) |  |
| `POST` | `/v1/users/{userId}/clients/{clientId}/offline/albums` | `UserService$UserRestClient.addOfflineAlbum` | `userId`, `clientId`, `albumId` | not reached – needs an offline-authorized device |  |
| `DELETE` | `/v1/users/{userId}/clients/{clientId}/offline/albums/{albumId}` | `UserService$UserRestClient.removeOfflineAlbum` | `userId`, `clientId`, `albumId` | not reached |  |
| `DELETE` | `/v1/users/{userId}/clients/{clientId}/offline/all` | `UserService$UserRestClient.removeAllOfflineContent` | `userId`, `clientId` | not reached |  |
| `GET` | `/v1/users/{userId}/clients/{clientId}/offline/playlists` | `UserService$UserRestClient.getOfflinePlaylists` | `userId`, `clientId`, `limit` | ⚠️ 400 – Bad request (no offline client) |  |
| `POST` | `/v1/users/{userId}/clients/{clientId}/offline/playlists` | `UserService$UserRestClient.addOfflinePlaylist` | `userId`, `clientId`, `playlistUuid` | not reached |  |
| `DELETE` | `/v1/users/{userId}/clients/{clientId}/offline/playlists/{playlistUuid}` | `UserService$UserRestClient.removeOfflinePlaylist` | `userId`, `clientId`, `playlistUuid` | not reached |  |
| `GET` | `/v1/users/{userId}/contentCreatorInfo` | `ContentCreatorInfoService.getContentCreatorInfo` | `userId` | ✅ 200 | [→](upload-creator) |
| `POST` | `/v1/users/{userId}/contentCreatorInfo` | `ContentCreatorInfoService.setContentCreatorInfo` | `userId`, `optedInForUploader`, `acceptedTerms` | not executed – opts in to uploads and accepts terms | [→](upload-creator) |
| `POST` | `/v1/users/{userId}/earlyAccessProgram` | `UserService.setEarlyAccessProgramEnabled` | `userId`, `active` | ✅ 200 – same value | [→](user-onboarding) |
| `POST` | `/v1/users/{userId}/email/verify` | `UserService.requestVerificationEmail` | `userId` | not executed – sends an email | [→](user-account) |
| `DELETE` | `/v1/users/{userId}/facebook` | `UserService.removeFacebookConnection` | `userId` | not executed – account link | [→](user-account) |
| `POST` | `/v1/users/{userId}/facebook` | `UserService.addFacebookConnection` | `userId`, `accessToken` | not executed – needs a Facebook token | [→](user-account) |
| `GET` | `/v1/users/{userId}/favorites/albums` | `UserService$UserRestClient.getFavoriteAlbums` | `userId`, `limit`, `order`, `orderDirection` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/favorites/albums` | `SearchAlbumsService.getFavoriteAlbums` | `userId`, `limit` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/favorites/artists?limit=9999` | `MyCollectionV1Service.getFavoriteArtists` | `userId` | ✅ 200 |  |
| `GET` | `/v2/users/{userId}/favorites/mixes` | `UserService$UserRestClient.getFavoriteMixes` | `userId`, `offset`, `limit` | ⚠️ 404 – client_error |  |
| `DELETE` | `/v1/users/{userId}/favorites/mixes/{mixId}/remove` | `UserService$UserRestClient.removeFavoriteMix` | `userId`, `mixId` | ⚠️ 404 – removed by TIDAL, use my-collection/mixes/remove |  |
| `GET` | `/v1/users/{userId}/favorites/playlists` | `UserService$UserRestClient.getFavoritePlaylists` | `userId`, `limit` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/favorites/playlists` | `SearchPlaylistsService.getFavoritePlaylists` | `userId`, `limit` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/favorites/tracks` | `UserService$UserRestClient.getFavoriteTracks` | `userId`, `limit` | ✅ 200 |  |
| `POST` | `/v1/users/{userId}/favorites/tracks` | `UserService$UserRestClient.addFavoriteTrack` | `userId`, `trackId` | ✅ 200 – web test |  |
| `DELETE` | `/v1/users/{userId}/favorites/tracks/{trackId}` | `UserService$UserRestClient.removeFavoriteTrack` | `userId`, `trackId` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/favorites/videos` | `UserService$UserRestClient.getFavoriteVideos` | `userId`, `offset`, `limit` | ✅ 200 |  |
| `POST` | `/v1/users/{userId}/favorites/videos` | `UserService$UserRestClient.addFavoriteVideos` | `userId`, `videoIds` | ✅ 200 – web test |  |
| `DELETE` | `/v1/users/{userId}/favorites/videos/{videoId}` | `UserService$UserRestClient.removeFavoriteVideo` | `userId`, `videoId` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/handovertoken` | `UserService$UserRestClient.getHandoverToken` | `userId` | ✅ 200 | [→](legacy-status) |
| `DELETE` | `/v1/users/{userId}/onboarding` | `TooltipService.removeAll` | `userId` | ✅ 200 – all flags restored afterwards | [→](user-onboarding) |
| `GET` | `/v1/users/{userId}/onboarding` | `TooltipService.getAll` | `userId` | ✅ 200 | [→](user-onboarding) |
| `GET` | `/v1/users/{userId}/onboarding` | `UsersService.getOnboarding` | `userId`, `countryCode` | ✅ 200 | [→](user-onboarding) |
| `POST` | `/v1/users/{userId}/onboarding` | `TooltipService.report` | `userId`, `key` | ✅ 200 | [→](user-onboarding) |
| `POST` | `/v1/users/{userId}/onboarding` | `UsersService.report` | `userId`, `countryCode`, `key` | ✅ 200 | [→](user-onboarding) |
| `POST` | `/v1/users/{userId}/onboarding/list` | `TooltipService.reportList` | `userId`, `keys` | ✅ 200 – repeated `keys` fields | [→](user-onboarding) |
| `GET` | `/v1/users/{userId}/playlists` | `UserService$UserRestClient.getPlaylists` | `userId`, `limit` | ✅ 200 |  |
| `GET` | `/v1/users/{userId}/playlists` | `SearchPlaylistsService.getPlaylists` | `userId`, `limit` | ✅ 200 |  |
| `POST` | `/v1/users/{userId}/playlists` | `UserService$UserRestClient.createPlaylist` | `userId`, `title`, `description` | ✅ 201 – web test |  |
| `GET` | `/v1/users/{userId}/progress/items` | `ProgressService.getProgresses` | `userId`, `ids` | ✅ 200 | [→](user-progress) |
| `GET` | `/v1/users/{userId}/subscription` | `UserSubscriptionService.getSubscription` | `userId` | ✅ 200 |  |

###### videos
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/videos/{id}` | `VideoService$VideoRestClient.getVideo` | `id` | ✅ 200 |  |
| `GET` | `/v1/videos/{id}/credits` | `CreditsService.getVideoCredits` | `id`, `includeContributors` | ✅ 200 | [→](video-extras) |
| `GET` | `/v1/videos/{id}/playbackinfopostpaywall` | `VideoService$VideoRestClient.getPlaybackInfoPostPaywall` | `id`, `playbackmode`, `assetpresentation`, `videoquality`, `streamingsessionid`, `playlistuuid` | ✅ 200 |  |
| `GET` | `/v1/videos/{id}/recommendations` | `VideoService$VideoRestClient.getRecommendations` | `id`, `limit` | ⚠️ 500 – Ooops, an unexpected error occurred (server error at TIDAL) | [→](video-extras) |

###### welcome
| Method | Url | Android service.method | Parameters | Live test 2026-11-01 | Doc |
|---|---|---|---|---|---|
| `GET` | `/v1/welcome/artists/{artistId}/similar` | `WelcomeService.getSimilarArtists` | `artistId`, `limit` | ✅ 200 | [→](welcome-artists) |
| `GET` | `/v1/welcome/categories/artists` | `WelcomeService.getArtistWithCategories` | `limit`, `locale` | ✅ 200 | [→](welcome-artists) |
| `GET` | `/v1/welcome/categories/{categoryId}/artists` | `WelcomeService.getMoreArtists` | `categoryId`, `offset`, `limit` | ✅ 200 | [→](welcome-artists) |
| `POST` | `/v1/welcome/users/artists` | `WelcomeService.postSelectedArtistIds` | `artistIds` | not executed – overwrites the taste profile | [→](welcome-artists) |
