The Android app (`com.aspiro.tidal` 2.215.0) contains the experimentation and feature flag client of Block (TIDAL's parent company, package `com.squareup.experiments`).

### Feature Flags / Experiments (not executed)
* Other calls: `POST /1.0/experimentation/get-experiments`, `POST /1.0/experimentation/activate-experiment`, `POST /1.0/experimentation/record-exclusion`, `POST /1.0/experimentation/track-event` (all with JSON body).
* Not executed: the host is configured at runtime and could not be identified; `ec.tidal.com` answers `403`. The tracking calls would also write analytics data.
##### Method
```POST```
##### Url
```{experimentation host}/1.0/features/get-flags```
##### Header
(Block experimentation credentials)
