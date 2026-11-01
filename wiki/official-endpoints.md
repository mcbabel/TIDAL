Generated from the official OpenAPI spec version `1.10.218` (2026-11-01): https://tidal-music.github.io/tidal-api-reference/tidal-api-oas.json

All 438 operations of the spec: 101 open to third-party apps (`THIRD_PARTY`), 336 internal to TIDAL's own apps (`INTERNAL`), 1 partner-only (`PARTNER`). Each resource links to its reference page with parameters, bodies and attributes.

Base url: ```https://openapi.tidal.com/v2```

Guides: [Overview](OfficialAPI), [Migration Guide](Migration), [Get Track](official-track), [Search](official-searchResults), [TrackManifests](official-trackManifests), [Playlists](official-playlists), [User Collections](official-userCollections), [User](official-users)


###### [acceptedTerms](official-ref-acceptedTerms)
```GET /acceptedTerms``` Get multiple acceptedTerms. `INTERNAL`, Auth: PKCE\
```POST /acceptedTerms``` Create single acceptedTerm. `INTERNAL`, Auth: PKCE\
```GET /acceptedTerms/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /acceptedTerms/{id}/relationships/terms``` Get terms relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [albums](official-ref-albums)
```GET /albums``` Get multiple albums. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```POST /albums``` Create single album. `INTERNAL`, Auth: PKCE\
```DELETE /albums/{id}``` Delete single album. `INTERNAL`, Auth: PKCE\
```GET /albums/{id}``` Get single album. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /albums/{id}``` Update single album. `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/albumStatistics``` Get albumStatistics relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/artists``` Get artists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /albums/{id}/relationships/artists``` Update artists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/coverArt``` Get coverArt relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /albums/{id}/relationships/coverArt``` Update coverArt relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/genres``` Get genres relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /albums/{id}/relationships/items``` Update items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/priceConfig``` Get priceConfig relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/providers``` Get providers relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/replacement``` Get replacement relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/shares``` Get shares relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/similarAlbums``` Get similarAlbums relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /albums/{id}/relationships/suggestedCoverArts``` Get suggestedCoverArts relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /albums/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [albumStatistics](official-ref-albumStatistics)
```GET /albumStatistics/{id}``` Get single albumStatistic. `INTERNAL`, Auth: PKCE\
```GET /albumStatistics/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [appreciations](official-ref-appreciations)
```POST /appreciations``` Create single appreciation. `INTERNAL`, Auth: PKCE

###### [artistBiographies](official-ref-artistBiographies)
```GET /artistBiographies/{id}``` Get single artistBiographie. `INTERNAL`, Auth: Client Credentials, PKCE\
```PATCH /artistBiographies/{id}``` Update single artistBiographie. `INTERNAL`, Auth: PKCE\
```GET /artistBiographies/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [artistClaims](official-ref-artistClaims)
```GET /artistClaims``` Get multiple artistClaims. `INTERNAL`, Auth: PKCE\
```POST /artistClaims``` Create single artistClaim. `INTERNAL`, Auth: PKCE\
```DELETE /artistClaims/{id}``` Delete single artistClaim. `INTERNAL`, Auth: PKCE\
```GET /artistClaims/{id}``` Get single artistClaim. `INTERNAL`, Auth: PKCE\
```PATCH /artistClaims/{id}``` Update single artistClaim. `INTERNAL`, Auth: PKCE\
```GET /artistClaims/{id}/relationships/acceptedArtists``` Get acceptedArtists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```PATCH /artistClaims/{id}/relationships/acceptedArtists``` Update acceptedArtists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artistClaims/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artistClaims/{id}/relationships/recommendedArtists``` Get recommendedArtists relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [artistClaimStatuses](official-ref-artistClaimStatuses)
```GET /artistClaimStatuses``` Get multiple artistClaimStatuses. `INTERNAL`, Auth: PKCE

###### [artistRoles](official-ref-artistRoles)
```GET /artistRoles/{id}``` Get single artistRole. `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [artists](official-ref-artists)
```GET /artists``` Get multiple artists. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```POST /artists``` Create single artist. `INTERNAL`, Auth: PKCE\
```GET /artists/{id}``` Get single artist. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /artists/{id}``` Update single artist. `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/albums``` Get albums relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/bannerArt``` Get bannerArt relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```PATCH /artists/{id}/relationships/bannerArt``` Update bannerArt relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/biography``` Get biography relationship ("to-one"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/claimStatus``` Get claimStatus relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/followers``` Get followers relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```DELETE /artists/{id}/relationships/following``` Delete from following relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/following``` Get following relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /artists/{id}/relationships/following``` Add to following relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/logoArt``` Get logoArt relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```PATCH /artists/{id}/relationships/logoArt``` Update logoArt relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/profileArt``` Get profileArt relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /artists/{id}/relationships/profileArt``` Update profileArt relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /artists/{id}/relationships/radio``` Get radio relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/roles``` Get roles relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/similarArtists``` Get similarArtists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/trackProviders``` Get trackProviders relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/tracks``` Get tracks relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artists/{id}/relationships/videos``` Get videos relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [artistSalesStatistics](official-ref-artistSalesStatistics)
```GET /artistSalesStatistics``` Get multiple artistSalesStatistics. `INTERNAL`, Auth: PKCE\
```GET /artistSalesStatistics/{id}/relationships/artist``` Get artist relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /artistSalesStatistics/{id}/relationships/topSellers``` Get topSellers relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [artistStreamsStatistics](official-ref-artistStreamsStatistics)
```GET /artistStreamsStatistics``` Get multiple artistStreamsStatistics. `INTERNAL`, Auth: PKCE\
```GET /artistStreamsStatistics/{id}/relationships/artist``` Get artist relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /artistStreamsStatistics/{id}/relationships/topTracks``` Get topTracks relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [artworkLibraries](official-ref-artworkLibraries)
```GET /artworkLibraries``` Get multiple artworkLibraries. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /artworkLibraries/{id}``` Get single artworkLibrarie. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /artworkLibraries/{id}/relationships/artworks``` Get artworks relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /artworkLibraries/{id}/relationships/randomArtwork``` Get randomArtwork relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [artworks](official-ref-artworks)
```GET /artworks``` Get multiple artworks. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```POST /artworks``` Create single artwork. `INTERNAL`, Auth: PKCE\
```GET /artworks/{id}``` Get single artwork. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /artworks/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [clientCertificates](official-ref-clientCertificates)
```POST /clientCertificates``` Create single clientCertificate. `INTERNAL`, Auth: PKCE\
```GET /clientCertificates/{id}``` Get single clientCertificate. `INTERNAL`, Auth: PKCE\
```GET /clientCertificates/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [clients](official-ref-clients)
```GET /clients``` Get multiple clients. `INTERNAL`, Auth: PKCE\
```POST /clients``` Create single client. `INTERNAL`, Auth: PKCE\
```DELETE /clients/{id}``` Delete single client. `INTERNAL`, Auth: PKCE\
```GET /clients/{id}``` Get single client. `INTERNAL`, Auth: PKCE\
```PATCH /clients/{id}``` Update single client. `INTERNAL`, Auth: PKCE\
```GET /clients/{id}/relationships/certificates``` Get certificates relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /clients/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [collaborationInviteRedemptions](official-ref-collaborationInviteRedemptions)
```POST /collaborationInviteRedemptions``` Create single collaborationInviteRedemption. `INTERNAL`, Auth: PKCE (scopes: playlists.write) **Deprecated**

###### [collaborationInvites](official-ref-collaborationInvites)
```GET /collaborationInvites``` Get multiple collaborationInvites. `INTERNAL`, Auth: PKCE **Deprecated**\
```POST /collaborationInvites``` Create single collaborationInvite. `INTERNAL`, Auth: PKCE (scopes: playlists.write) **Deprecated**\
```DELETE /collaborationInvites/{id}``` Delete single collaborationInvite. `INTERNAL`, Auth: PKCE (scopes: playlists.write) **Deprecated**\
```GET /collaborationInvites/{id}``` Get single collaborationInvite. `INTERNAL`, Auth: PKCE **Deprecated**\
```GET /collaborationInvites/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE **Deprecated**\
```GET /collaborationInvites/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE **Deprecated**

###### [comments](official-ref-comments)
```GET /comments``` Get multiple comments. `INTERNAL`, Auth: PKCE\
```POST /comments``` Create single comment. `INTERNAL`, Auth: PKCE\
```DELETE /comments/{id}``` Delete single comment. `INTERNAL`, Auth: PKCE\
```GET /comments/{id}``` Get single comment. `INTERNAL`, Auth: PKCE\
```PATCH /comments/{id}``` Update single comment. `INTERNAL`, Auth: PKCE\
```GET /comments/{id}/relationships/author``` Get author relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /comments/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /comments/{id}/relationships/parentComment``` Get parentComment relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [contentClaims](official-ref-contentClaims)
```GET /contentClaims``` Get multiple contentClaims. `INTERNAL`, Auth: PKCE\
```POST /contentClaims``` Create single contentClaim. `INTERNAL`, Auth: PKCE\
```GET /contentClaims/{id}``` Get single contentClaim. `INTERNAL`, Auth: PKCE\
```GET /contentClaims/{id}/relationships/claimedResource``` Get claimedResource relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /contentClaims/{id}/relationships/claimingArtist``` Get claimingArtist relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /contentClaims/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [credits](official-ref-credits)
```GET /credits/{id}``` Get single credit. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /credits/{id}/relationships/artist``` Get artist relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /credits/{id}/relationships/category``` Get category relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [downloads](official-ref-downloads)
```GET /downloads``` Get multiple downloads. `INTERNAL`, Auth: PKCE\
```GET /downloads/{id}``` Get single download. `INTERNAL`, Auth: PKCE\
```GET /downloads/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [dspSharingLinks](official-ref-dspSharingLinks)
```GET /dspSharingLinks``` Get multiple dspSharingLinks. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dspSharingLinks/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [dynamicModules](official-ref-dynamicModules)
```GET /dynamicModules``` Get multiple dynamicModules. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dynamicModules/{id}``` Get single dynamicModule. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dynamicModules/{id}/relationships/items``` Get items relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dynamicModules/{id}/relationships/seedItem``` Get seedItem relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [dynamicPages](official-ref-dynamicPages)
```GET /dynamicPages``` Get multiple dynamicPages. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dynamicPages/{id}/relationships/modules``` Get modules relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /dynamicPages/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [folderItems](official-ref-folderItems)
```GET /folderItems``` Get multiple folderItems. `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```POST /folderItems``` Create single folderItem. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```DELETE /folderItems/{id}``` Delete single folderItem. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /folderItems/{id}``` Get single folderItem. `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folderItems/{id}/relationships/breadcrumb``` Get breadcrumb relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folderItems/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folderItems/{id}/relationships/parent``` Get parent relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```PATCH /folderItems/{id}/relationships/parent``` Update parent relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /folderItems/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folderItems/{id}/relationships/subjectSharingSettings``` Get subjectSharingSettings relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.read)

###### [folders](official-ref-folders)
```GET /folders``` Get multiple folders. `INTERNAL`, Auth: Client Credentials, PKCE (scopes: collection.read)\
```POST /folders``` Create single folder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```DELETE /folders/{id}``` Delete single folder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /folders/{id}``` Get single folder. `INTERNAL`, Auth: Client Credentials, PKCE (scopes: collection.read)\
```PATCH /folders/{id}``` Update single folder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /folders/{id}/relationships/children``` Get children relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folders/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE (scopes: collection.read)\
```GET /folders/{id}/relationships/parent``` Get parent relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folders/{id}/relationships/preview``` Get preview relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /folders/{id}/relationships/shares``` Get shares relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)

###### [genres](official-ref-genres)
```GET /genres``` Get multiple genres. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /genres/{id}``` Get single genre. `INTERNAL`, Auth: Client Credentials, PKCE

###### [groups](official-ref-groups)
```GET /groups``` Get multiple groups. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /groups/{id}``` Get single group. `INTERNAL`, Auth: Client Credentials, PKCE

###### [installations](official-ref-installations)
```GET /installations``` Get multiple installations. `INTERNAL`, Auth: PKCE\
```POST /installations``` Create single installation. `INTERNAL`, Auth: PKCE\
```GET /installations/{id}``` Get single installation. `INTERNAL`, Auth: PKCE\
```DELETE /installations/{id}/relationships/offlineInventory``` Delete from offlineInventory relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /installations/{id}/relationships/offlineInventory``` Get offlineInventory relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /installations/{id}/relationships/offlineInventory``` Add to offlineInventory relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /installations/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [lyrics](official-ref-lyrics)
```POST /lyrics``` Create single lyric. `INTERNAL`, Auth: PKCE\
```DELETE /lyrics/{id}``` Delete single lyric. `INTERNAL`, Auth: PKCE\
```GET /lyrics/{id}``` Get single lyric. `INTERNAL`, Auth: Client Credentials, PKCE\
```PATCH /lyrics/{id}``` Update single lyric. `INTERNAL`, Auth: PKCE\
```GET /lyrics/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /lyrics/{id}/relationships/track``` Get track relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [manualArtistClaims](official-ref-manualArtistClaims)
```POST /manualArtistClaims``` Create single manualArtistClaim. `INTERNAL`, Auth: PKCE

###### [offlineTasks](official-ref-offlineTasks)
```GET /offlineTasks``` Get multiple offlineTasks. `INTERNAL`, Auth: PKCE\
```GET /offlineTasks/{id}``` Get single offlineTask. `INTERNAL`, Auth: PKCE\
```PATCH /offlineTasks/{id}``` Update single offlineTask. `INTERNAL`, Auth: PKCE\
```GET /offlineTasks/{id}/relationships/collection``` Get collection relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /offlineTasks/{id}/relationships/item``` Get item relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /offlineTasks/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [playlistGenerations](official-ref-playlistGenerations)
```GET /playlistGenerations``` Get multiple playlistGenerations. `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```POST /playlistGenerations``` Create single playlistGeneration. `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```GET /playlistGenerations/{id}``` Get single playlistGeneration. `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```GET /playlistGenerations/{id}/relationships/baseGeneration``` Get baseGeneration relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```GET /playlistGenerations/{id}/relationships/playlist``` Get playlist relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```DELETE /playlistGenerations/{id}/relationships/trackPreferences``` Delete from trackPreferences relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```GET /playlistGenerations/{id}/relationships/trackPreferences``` Get trackPreferences relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```PATCH /playlistGenerations/{id}/relationships/trackPreferences``` Update trackPreferences relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```POST /playlistGenerations/{id}/relationships/trackPreferences``` Add to trackPreferences relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.write)

###### [playlistGenerationSchedules](official-ref-playlistGenerationSchedules)
```GET /playlistGenerationSchedules``` Get multiple playlistGenerationSchedules. `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```POST /playlistGenerationSchedules``` Create single playlistGenerationSchedule. `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```DELETE /playlistGenerationSchedules/{id}``` Delete single playlistGenerationSchedule. `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```GET /playlistGenerationSchedules/{id}``` Get single playlistGenerationSchedule. `INTERNAL`, Auth: PKCE (scopes: playlists.read)\
```PATCH /playlistGenerationSchedules/{id}``` Update single playlistGenerationSchedule. `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```GET /playlistGenerationSchedules/{id}/relationships/playlist``` Get playlist relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: playlists.read)

###### [playlists](official-ref-playlists)
```GET /playlists``` Get multiple playlists. `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: playlists.read)\
```POST /playlists``` Create single playlist. `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```DELETE /playlists/{id}``` Delete single playlist. `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```GET /playlists/{id}``` Get single playlist. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /playlists/{id}``` Update single playlist. `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```DELETE /playlists/{id}/relationships/collaboratorProfiles``` Delete from collaboratorProfiles relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.write) **Deprecated**\
```GET /playlists/{id}/relationships/collaboratorProfiles``` Get collaboratorProfiles relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE **Deprecated**\
```GET /playlists/{id}/relationships/collaborators``` Get collaborators relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /playlists/{id}/relationships/coverArt``` Get coverArt relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /playlists/{id}/relationships/coverArt``` Update coverArt relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: playlists.write)\
```GET /playlists/{id}/relationships/curators``` Get curators relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```DELETE /playlists/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```GET /playlists/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /playlists/{id}/relationships/items``` Update items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```POST /playlists/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: playlists.write)\
```GET /playlists/{id}/relationships/ownerProfiles``` Get ownerProfiles relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE **Deprecated**\
```GET /playlists/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /playlists/{id}/relationships/suggestedCoverArts``` Get suggestedCoverArts relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [playQueues](official-ref-playQueues)
```GET /playQueues``` Get multiple playQueues. `INTERNAL`, Auth: PKCE\
```POST /playQueues``` Create single playQueue. `INTERNAL`, Auth: PKCE\
```DELETE /playQueues/{id}``` Delete single playQueue. `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}``` Get single playQueue. `INTERNAL`, Auth: PKCE\
```PATCH /playQueues/{id}``` Update single playQueue. `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}/relationships/changeEventStream``` Get changeEventStream relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}/relationships/current``` Get current relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```PATCH /playQueues/{id}/relationships/current``` Update current relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```DELETE /playQueues/{id}/relationships/future``` Delete from future relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}/relationships/future``` Get future relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```PATCH /playQueues/{id}/relationships/future``` Update future relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /playQueues/{id}/relationships/future``` Add to future relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /playQueues/{id}/relationships/past``` Get past relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [priceConfigurations](official-ref-priceConfigurations)
```GET /priceConfigurations``` Get multiple priceConfigurations. `INTERNAL`, Auth: Client Credentials, PKCE\
```POST /priceConfigurations``` Create single priceConfiguration. `INTERNAL`, Auth: PKCE\
```GET /priceConfigurations/{id}``` Get single priceConfiguration. `INTERNAL`, Auth: Client Credentials, PKCE

###### [providerOwners](official-ref-providerOwners)
```GET /providerOwners``` Get multiple providerOwners. `INTERNAL`, Auth: PKCE\
```GET /providerOwners/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /providerOwners/{id}/relationships/provider``` Get provider relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [providerProductInfos](official-ref-providerProductInfos)
```GET /providerProductInfos``` Get multiple providerProductInfos. `INTERNAL`, Auth: PKCE\
```GET /providerProductInfos/{id}/relationships/provider``` Get provider relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /providerProductInfos/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [providers](official-ref-providers)
```GET /providers/{id}``` Get single provider. `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [purchases](official-ref-purchases)
```GET /purchases``` Get multiple purchases. `INTERNAL`, Auth: PKCE\
```GET /purchases/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /purchases/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [reactions](official-ref-reactions)
```GET /reactions``` Get multiple reactions. `INTERNAL`, Auth: PKCE\
```POST /reactions``` Create single reaction. `INTERNAL`, Auth: PKCE\
```DELETE /reactions/{id}``` Delete single reaction. `INTERNAL`, Auth: PKCE\
```GET /reactions/{id}/relationships/author``` Get author relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /reactions/{id}/relationships/ownerProfiles``` Get ownerProfiles relationship ("to-many"). `INTERNAL`, Auth: PKCE **Deprecated**\
```GET /reactions/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [resourceGrants](official-ref-resourceGrants)
```GET /resourceGrants``` Get multiple resourceGrants. `INTERNAL`, Auth: PKCE\
```POST /resourceGrants``` Create single resourceGrant. `INTERNAL`, Auth: PKCE\
```DELETE /resourceGrants/{id}``` Delete single resourceGrant. `INTERNAL`, Auth: PKCE\
```GET /resourceGrants/{id}``` Get single resourceGrant. `INTERNAL`, Auth: PKCE\
```PATCH /resourceGrants/{id}``` Update single resourceGrant. `INTERNAL`, Auth: PKCE\
```GET /resourceGrants/{id}/relationships/grantee``` Get grantee relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /resourceGrants/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [resourceSharingSettings](official-ref-resourceSharingSettings)
```GET /resourceSharingSettings``` Get multiple resourceSharingSettings. `INTERNAL`, Auth: PKCE\
```GET /resourceSharingSettings/{id}``` Get single resourceSharingSetting. `INTERNAL`, Auth: PKCE\
```GET /resourceSharingSettings/{id}/relationships/grants``` Get grants relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /resourceSharingSettings/{id}/relationships/shares``` Get shares relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /resourceSharingSettings/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [savedShares](official-ref-savedShares)
```POST /savedShares``` Create single savedShare. `INTERNAL`, Auth: PKCE

###### [scopes](official-ref-scopes)
```GET /scopes``` Get multiple scopes. `INTERNAL`, Auth: PKCE

###### [searchHistoryEntries](official-ref-searchHistoryEntries)
```DELETE /searchHistoryEntries/{id}``` Delete single searchHistoryEntrie. `INTERNAL`, Auth: PKCE (scopes: search.write)

###### [searchResults](official-ref-searchResults)
```GET /searchResults``` Get search results by query. `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/albums``` Get albums relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/artists``` Get artists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/playlists``` Get playlists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/topHits``` Get topHits relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/tracks``` Get tracks relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchResults/{id}/relationships/videos``` Get videos relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)

###### [searchSuggestions](official-ref-searchSuggestions)
```GET /searchSuggestions``` Get search suggestions by query. `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchSuggestions/{id}/relationships/directHits``` Get directHits relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: search.read)\
```GET /searchSuggestions/{id}/relationships/history``` Get history relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: search.read)

###### [shares](official-ref-shares)
```GET /shares``` Get multiple shares. `INTERNAL`, Auth: Client Credentials, PKCE\
```POST /shares``` Create single share. `INTERNAL`, Auth: PKCE\
```DELETE /shares/{id}``` Delete single share. `INTERNAL`, Auth: PKCE\
```GET /shares/{id}``` Get single share. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /shares/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /shares/{id}/relationships/sharedResources``` Get sharedResources relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE

###### [squareConnections](official-ref-squareConnections)
```POST /squareConnections``` Create single squareConnection. `INTERNAL`, Auth: PKCE\
```GET /squareConnections/{id}``` Get single squareConnection. `INTERNAL`, Auth: PKCE\
```GET /squareConnections/{id}/relationships/selectedSite``` Get selectedSite relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```PATCH /squareConnections/{id}/relationships/selectedSite``` Update selectedSite relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /squareConnections/{id}/relationships/sites``` Get sites relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [squareItems](official-ref-squareItems)
```GET /squareItems``` Get multiple squareItems. `INTERNAL`, Auth: PKCE\
```DELETE /squareItems/{id}``` Delete single squareItem. `INTERNAL`, Auth: PKCE\
```GET /squareItems/{id}``` Get single squareItem. `INTERNAL`, Auth: PKCE\
```PATCH /squareItems/{id}``` Update single squareItem. `INTERNAL`, Auth: PKCE\
```GET /squareItems/{id}/relationships/artworks``` Get artworks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```PATCH /squareItems/{id}/relationships/artworks``` Update artworks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /squareItems/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /squareItems/{id}/relationships/variations``` Get variations relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```PATCH /squareItems/{id}/relationships/variations``` Update variations relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [squareItemVariationPhysicalCounts](official-ref-squareItemVariationPhysicalCounts)
```POST /squareItemVariationPhysicalCounts``` Create single squareItemVariationPhysicalCount. `INTERNAL`, Auth: PKCE

###### [squareItemVariations](official-ref-squareItemVariations)
```POST /operations``` Commit atomic resource operations. `INTERNAL`, Auth: PKCE\
```POST /squareItemVariations``` Create single squareItemVariation. `INTERNAL`, Auth: PKCE\
```DELETE /squareItemVariations/{id}``` Delete single squareItemVariation. `INTERNAL`, Auth: PKCE\
```GET /squareItemVariations/{id}``` Get single squareItemVariation. `INTERNAL`, Auth: PKCE\
```PATCH /squareItemVariations/{id}``` Update single squareItemVariation. `INTERNAL`, Auth: PKCE\
```GET /squareItemVariations/{id}/relationships/artworks``` Get artworks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```PATCH /squareItemVariations/{id}/relationships/artworks``` Update artworks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /squareItemVariations/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [squareSites](official-ref-squareSites)
```DELETE /squareSites/{id}/relationships/items``` Delete from items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /squareSites/{id}/relationships/items``` Get items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /squareSites/{id}/relationships/items``` Add to items relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [stripeConnections](official-ref-stripeConnections)
```GET /stripeConnections``` Get multiple stripeConnections. `INTERNAL`, Auth: PKCE\
```POST /stripeConnections``` Create single stripeConnection. `INTERNAL`, Auth: PKCE\
```GET /stripeConnections/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [stripeDashboardLinks](official-ref-stripeDashboardLinks)
```GET /stripeDashboardLinks``` Get multiple stripeDashboardLinks. `INTERNAL`, Auth: PKCE\
```GET /stripeDashboardLinks/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [subscriptionPriceChangeDecisions](official-ref-subscriptionPriceChangeDecisions)
```GET /subscriptionPriceChangeDecisions``` Get multiple subscriptionPriceChangeDecisions. `INTERNAL`, Auth: PKCE\
```POST /subscriptionPriceChangeDecisions``` Create single subscriptionPriceChangeDecision. `INTERNAL`, Auth: PKCE\
```PATCH /subscriptionPriceChangeDecisions/{id}``` Update single subscriptionPriceChangeDecision. `INTERNAL`, Auth: PKCE\
```GET /subscriptionPriceChangeDecisions/{id}/relationships/priceChange``` Get priceChange relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [temporaryUserTokens](official-ref-temporaryUserTokens)
```POST /temporaryUserTokens``` Create single temporaryUserToken. `INTERNAL`, Auth: PKCE\
```GET /temporaryUserTokens/{id}``` Get single temporaryUserToken. `INTERNAL`, Auth: PKCE\
```GET /temporaryUserTokens/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [terms](official-ref-terms)
```GET /terms``` Get multiple terms. `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /terms/{id}``` Get single term. `INTERNAL`, Auth: Client Credentials, PKCE

###### [trackFiles](official-ref-trackFiles)
```GET /trackFiles/{id}``` Get single trackFile. `PARTNER`, Auth: Client Credentials, PKCE (scopes: playback)

###### [trackManifests](official-ref-trackManifests)
```GET /trackManifests/{id}``` Get single trackManifest. `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: playback)

###### [tracks](official-ref-tracks)
```GET /tracks``` Get multiple tracks. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```POST /tracks``` Create single track. `INTERNAL`, Auth: PKCE\
```DELETE /tracks/{id}``` Delete single track. `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}``` Get single track. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /tracks/{id}``` Update single track. `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/albums``` Get albums relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /tracks/{id}/relationships/albums``` Update albums relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/artists``` Get artists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```PATCH /tracks/{id}/relationships/artists``` Update artists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/credits``` Get credits relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/download``` Get download relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/genres``` Get genres relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/lyrics``` Get lyrics relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/metadataStatus``` Get metadataStatus relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/priceConfig``` Get priceConfig relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/providers``` Get providers relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/radio``` Get radio relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/replacement``` Get replacement relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/shares``` Get shares relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/similarTracks``` Get similarTracks relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/sourceFile``` Get sourceFile relationship ("to-one"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/suggestedTracks``` Get suggestedTracks relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /tracks/{id}/relationships/trackStatistics``` Get trackStatistics relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /tracks/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [tracksMetadataStatus](official-ref-tracksMetadataStatus)
```GET /tracksMetadataStatus/{id}``` Get single tracksMetadataStatu. `INTERNAL`, Auth: PKCE

###### [trackSourceFiles](official-ref-trackSourceFiles)
```POST /trackSourceFiles``` Create single trackSourceFile. `INTERNAL`, Auth: PKCE\
```GET /trackSourceFiles/{id}``` Get single trackSourceFile. `INTERNAL`, Auth: PKCE\
```GET /trackSourceFiles/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [trackStatistics](official-ref-trackStatistics)
```GET /trackStatistics/{id}``` Get single trackStatistic. `INTERNAL`, Auth: PKCE\
```GET /trackStatistics/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [usageRules](official-ref-usageRules)
```POST /usageRules``` Create single usageRule. `INTERNAL`, Auth: PKCE\
```GET /usageRules/{id}``` Get single usageRule. `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [userCollectionAlbums](official-ref-userCollectionAlbums)
```GET /userCollectionAlbums/{id}``` Get single userCollectionAlbum. `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```DELETE /userCollectionAlbums/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionAlbums/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionAlbums/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionAlbums/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)

###### [userCollectionArtists](official-ref-userCollectionArtists)
```GET /userCollectionArtists/{id}``` Get single userCollectionArtist. `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```DELETE /userCollectionArtists/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionArtists/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionArtists/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionArtists/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)

###### [userCollectionFolders](official-ref-userCollectionFolders)
```GET /userCollectionFolders``` Get multiple userCollectionFolders. `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionFolders``` Create single userCollectionFolder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```DELETE /userCollectionFolders/{id}``` Delete single userCollectionFolder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionFolders/{id}``` Get single userCollectionFolder. `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```PATCH /userCollectionFolders/{id}``` Update single userCollectionFolder. `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```DELETE /userCollectionFolders/{id}/relationships/items``` Delete from items relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionFolders/{id}/relationships/items``` Get items relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionFolders/{id}/relationships/items``` Add to items relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionFolders/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: collection.read)\
```GET /userCollectionFolders/{id}/relationships/userCollection``` Get userCollection relationship ("to-one"). `INTERNAL`, Auth: PKCE (scopes: collection.read)

###### [userCollectionPlaylists](official-ref-userCollectionPlaylists)
```GET /userCollectionPlaylists/{id}``` Get single userCollectionPlaylist. `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```DELETE /userCollectionPlaylists/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionPlaylists/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionPlaylists/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionPlaylists/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)

###### [userCollectionSaveForLaters](official-ref-userCollectionSaveForLaters)
```GET /userCollectionSaveForLaters/{id}``` Get single userCollectionSaveForLater. `INTERNAL`, Auth: PKCE\
```DELETE /userCollectionSaveForLaters/{id}/relationships/items``` Delete from items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userCollectionSaveForLaters/{id}/relationships/items``` Get items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /userCollectionSaveForLaters/{id}/relationships/items``` Add to items relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userCollectionSaveForLaters/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [userCollectionTracks](official-ref-userCollectionTracks)
```GET /userCollectionTracks/{id}``` Get single userCollectionTrack. `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```DELETE /userCollectionTracks/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionTracks/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionTracks/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionTracks/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)

###### [userCollectionVideos](official-ref-userCollectionVideos)
```GET /userCollectionVideos/{id}``` Get single userCollectionVideo. `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```DELETE /userCollectionVideos/{id}/relationships/items``` Delete from items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionVideos/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)\
```POST /userCollectionVideos/{id}/relationships/items``` Add to items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.write)\
```GET /userCollectionVideos/{id}/relationships/owners``` Get owners relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: collection.read)

###### [userDailyMixes](official-ref-userDailyMixes)
```GET /userDailyMixes/{id}``` Get single userDailyMixe. `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)\
```GET /userDailyMixes/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)

###### [userDataExportRequests](official-ref-userDataExportRequests)
```POST /userDataExportRequests``` Create single userDataExportRequest. `INTERNAL`, Auth: PKCE

###### [userDiscoveryMixes](official-ref-userDiscoveryMixes)
```GET /userDiscoveryMixes/{id}``` Get single userDiscoveryMixe. `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)\
```GET /userDiscoveryMixes/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)

###### [userFeedItems](official-ref-userFeedItems)
```GET /userFeedItems``` Get multiple userFeedItems. `INTERNAL`, Auth: PKCE\
```GET /userFeedItems/{id}/relationships/actors``` Get actors relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userFeedItems/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [userFeeds](official-ref-userFeeds)
```GET /userFeeds/{id}``` Get single userFeed. `INTERNAL`, Auth: PKCE\
```PATCH /userFeeds/{id}``` Update single userFeed. `INTERNAL`, Auth: PKCE

###### [userNewReleaseMixes](official-ref-userNewReleaseMixes)
```GET /userNewReleaseMixes/{id}``` Get single userNewReleaseMixe. `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)\
```GET /userNewReleaseMixes/{id}/relationships/items``` Get items relationship ("to-many"). `THIRD_PARTY`, Auth: PKCE (scopes: recommendations.read)

###### [userOfflineMixes](official-ref-userOfflineMixes)
```GET /userOfflineMixes/{id}``` Get single userOfflineMixe. `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```GET /userOfflineMixes/{id}/relationships/items``` Get items relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: recommendations.read)

###### [userPlaybackStates](official-ref-userPlaybackStates)
```GET /userPlaybackStates/{id}``` Get single userPlaybackState. `INTERNAL`, Auth: PKCE\
```PATCH /userPlaybackStates/{id}``` Update single userPlaybackState. `INTERNAL`, Auth: PKCE\
```GET /userPlaybackStates/{id}/relationships/activePlayer``` Get activePlayer relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```PATCH /userPlaybackStates/{id}/relationships/activePlayer``` Update activePlayer relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```DELETE /userPlaybackStates/{id}/relationships/availablePlayers``` Delete from availablePlayers relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userPlaybackStates/{id}/relationships/availablePlayers``` Get availablePlayers relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```POST /userPlaybackStates/{id}/relationships/availablePlayers``` Add to availablePlayers relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userPlaybackStates/{id}/relationships/changeEventStream``` Get changeEventStream relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /userPlaybackStates/{id}/relationships/playQueue``` Get playQueue relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```PATCH /userPlaybackStates/{id}/relationships/playQueue``` Update playQueue relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [userRecommendationBlocks](official-ref-userRecommendationBlocks)
```GET /userRecommendationBlocks/{id}``` Get single userRecommendationBlock. `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```DELETE /userRecommendationBlocks/{id}/relationships/artists``` Delete from artists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userRecommendationBlocks/{id}/relationships/artists``` Get artists relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```POST /userRecommendationBlocks/{id}/relationships/artists``` Add to artists relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userRecommendationBlocks/{id}/relationships/owners``` Get owners relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```DELETE /userRecommendationBlocks/{id}/relationships/tracks``` Delete from tracks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userRecommendationBlocks/{id}/relationships/tracks``` Get tracks relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```POST /userRecommendationBlocks/{id}/relationships/tracks``` Add to tracks relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```DELETE /userRecommendationBlocks/{id}/relationships/videos``` Delete from videos relationship ("to-many"). `INTERNAL`, Auth: PKCE\
```GET /userRecommendationBlocks/{id}/relationships/videos``` Get videos relationship ("to-many"). `INTERNAL`, Auth: PKCE (scopes: recommendations.read)\
```POST /userRecommendationBlocks/{id}/relationships/videos``` Add to videos relationship ("to-many"). `INTERNAL`, Auth: PKCE

###### [userReports](official-ref-userReports)
```POST /userReports``` Create single userReport. `INTERNAL`, Auth: PKCE

###### [users](official-ref-users)
```GET /users/{id}``` Get single user. `THIRD_PARTY`, Auth: PKCE (scopes: user.read)\
```GET /users/{id}/relationships/artist``` Get artist relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [userSubscriptionPriceChanges](official-ref-userSubscriptionPriceChanges)
```GET /userSubscriptionPriceChanges``` Get multiple userSubscriptionPriceChanges. `INTERNAL`, Auth: PKCE\
```GET /userSubscriptionPriceChanges/{id}/relationships/decision``` Get decision relationship ("to-one"). `INTERNAL`, Auth: PKCE

###### [videoManifests](official-ref-videoManifests)
```GET /videoManifests/{id}``` Get single videoManifest. `THIRD_PARTY`, Auth: Client Credentials, PKCE (scopes: playback)

###### [videos](official-ref-videos)
```GET /videos``` Get multiple videos. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}``` Get single video. `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/albums``` Get albums relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/artists``` Get artists relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/credits``` Get credits relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/providers``` Get providers relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/replacement``` Get replacement relationship ("to-one"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/similarVideos``` Get similarVideos relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/suggestedVideos``` Get suggestedVideos relationship ("to-many"). `INTERNAL`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/thumbnailArt``` Get thumbnailArt relationship ("to-many"). `THIRD_PARTY`, Auth: Client Credentials, PKCE\
```GET /videos/{id}/relationships/usageRules``` Get usageRules relationship ("to-one"). `THIRD_PARTY`, Auth: Client Credentials, PKCE

###### [viewerContexts](official-ref-viewerContexts)
```GET /viewerContexts``` Get multiple viewerContexts. `INTERNAL`, Auth: PKCE\
```GET /viewerContexts/{id}``` Get single viewerContext. `INTERNAL`, Auth: PKCE\
```GET /viewerContexts/{id}/relationships/subject``` Get subject relationship ("to-one"). `INTERNAL`, Auth: PKCE\
```GET /viewerContexts/{id}/relationships/viewer``` Get viewer relationship ("to-one"). `INTERNAL`, Auth: PKCE
