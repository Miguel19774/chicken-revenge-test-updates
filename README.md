# Chicken Revenge TEST updates

This repository is reserved for TEST APK release assets and update metadata.

- Channel: `TEST`
- Android package: `com.miguel.chickenrevenge.debug`
- Stable metadata path: `test/version.json`
- APK files belong in GitHub Releases, under immutable `test-v<version>` tags.
- Only publish metadata after the referenced signed APK has been uploaded and verified.
- Anonymous access to both metadata and APK is required by the app; a private repository does not provide it.

Do not upload source code, MASTER assets, signing keys, credentials, or production builds here.

The first APK with a configured update URL must be installed manually over the existing TEST app. Subsequent APKs must retain the package and signing certificate and use a strictly higher versionCode. On-device progress retention must be tested; automated policy tests alone do not establish it.
