# X Patch

One Morphe patch source, six selectable enhancements for X. **Keep your existing source:** update it; no need to add a second source.

## Install or update
Source: https://github.com/rikunode/x-feed-cleanup-patches

Stable version: 1.12.2-x.6 · 6 patches · X **12.31.0-prod.01** / **12.32.0-prod.01**.

| Patch | Function |
|---|---|
| Fix external post links | Open linked posts without requiring Home / For You |
| Hide Find more | Hide Discover more recommendations |
| Hide Who to follow | Hide follow recommendations |
| Hide sports scores | Suppress sports ScoreCard tiles and live-game pills (experimental behavior) |
| Hide search relevance prompt | Hide yes/no relevance feedback card in X Search (experimental behavior) |
| Copy media URL | Copy image/video/GIF direct URLs from post options or the native media long-press menu |

All six can be selected for **the same X version** in one patching run. The last two filters have been merged from the earlier five-patch beta without removing the existing URL copy patch.
Version x.6 preserves x.5's native image/video long-press hook in X 12.31.0 and fixes its conditional row insertion and media URL extraction (`com.x.urt.items.post.media.x`) without changing the existing menu items. The new row is constructed before attempting URL extraction. Tapping it reads the actual image URL or video/GIF MP4 variants, choosing original photo quality or highest bitrate. Missing URLs show a message rather than hiding the row. The earlier x.4 hook remains unchanged. Real-APK patch application and isolated synthetic menu/URL tests passed; actual device UI and clipboard use must still be verified. The video-viewer overflow menu is not modified.

**Prerelease toggle:** Morphe compares stable and dev manifests and chooses the newer version. This stable 1.12.2-x.6 is newer than the old dev `1.12.1-legacy.4-beta.4`; switching the toggle off is not needed to get the latest unified version.

**Display name:** X Patch. If the source has a custom local name, change it using the pencil icon in Morphe.

## Verify
`python3 scripts/test-morphe-metadata.py`, `bash scripts/test-recommendation-filter.sh` and `./gradlew :patches:buildAndroid :patches:test` validate metadata, Java fixtures, and the patch bundle. Full patch application requires a compatible X APK; actual UI should be tested on an Android device.

## License
GNU GPLv3 — see LICENSE.
