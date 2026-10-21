# Chicken Revenge — TEST update publication

Status: **prepared; not live**. Repository access is public. No Release APK has been published yet.

## Prepared signed APKs

| Version | versionCode | APK asset name | Bytes | Metadata candidate |
| --- | ---: | --- | ---: | --- |
| 0.3.25-test-debug | 232 | ChickenRevenge-v0.3.25-TEST.apk | 292852233 | [0.3.25](candidates/0.3.25.version.json) |
| 0.3.26-test-debug | 233 | ChickenRevenge-v0.3.26-TEST.apk | 292852233 | [0.3.26](candidates/0.3.26.version.json) |

Package: `com.miguel.chickenrevenge.debug`.
Retained signing certificate SHA-256: `fb8dcd962cff92eab4f2306db8c655ded45b2961a9e573d97037f9c25001c115`.
This certificate fingerprint is public verification data, not a signing key.

Both APKs have this configured UPDATE_METADATA_URL:
`https://raw.githubusercontent.com/Miguel19774/chicken-revenge-test-updates/main/test/version.json`

The runtime file `test/version.json` is intentionally not published yet. Candidate files are preparation records, not live update announcements. Their APK URLs are reserved targets and do not establish that the assets exist.

## Publication order

1. Publish the signed APKs as GitHub Release assets under tags `test-v0.3.25` and `test-v0.3.26`, using the exact asset names above. Mark these releases as prereleases. Do not overwrite an asset with different bytes under the same version.
2. Download each APK anonymously from its Release URL. Verify its exact size, SHA-256, package, Android signature and versionCode. Confirm that actual HTTPS redirect hosts are supported by the app's allowlist (`github.com`, `release-assets.githubusercontent.com`).
3. Only after the target APK passes verification, copy the complete 0.3.26 candidate JSON to `test/version.json` and verify anonymous HTTP 200 and correct JSON content.
4. Manually install 0.3.25 TEST over the previous TEST app without uninstalling. Version 0.3.24 has no update URL and cannot discover this bootstrap automatically.
5. Exercise the in-app update from 0.3.25 to 0.3.26 on Android, recording levels, stars, coins, purchases, language and settings before and after. Test offline, cancellation, retry and foreground/resume. A successful host test does not prove device data retention.

## Verification status

- 72 host-side updater tests and 12 metadata preparation tests passed before preparing these candidates.
- APK hashes, sizes, package, signing certificate, versions, ZIP alignment and embedded update URL were verified.
- All 506 resource files are byte-identical to 0.3.24 TEST.
- Prepared APKs and metadata were checked for accidental signing keys, source archives and recognizable credential formats; none were found.
- Release download, real Android installation and progress retention tests remain pending.

## Current publishing limitation

The connected GitHub interface supports repository reads and Git/content writes. Its exposed operations do not include Release creation or Release asset upload. Reading a Release collection is not permission or capability to upload an APK. No browser or manual login was used for this metadata preparation.

Keep game sources, MASTER assets, keystores, private keys, credentials and PRODUCTION builds out of this distribution repository.
