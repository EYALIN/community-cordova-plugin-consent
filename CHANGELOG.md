# Changelog

All notable changes to this project will be documented in this file.

## [3.0.3] - 2026-09-30

### Fixed
- `canRequestAds()` (Android) now returns a real boolean instead of a stringified `"true"`/`"false"`
- `privacyOptionsRequirementStatus()` (Android) now returns the numeric `PrivacyOptionsRequirementStatus` enum value (0/1/2), mapped the same way `getConsentStatus()` maps its native status, instead of the raw native enum name string
- Updated `Promise<PrivacyOptionsRequirementStatus>` / `Promise<boolean>` typings to match

## [3.0.1] - 2026-01-18

### Changed
- Updated iOS GoogleUserMessagingPlatform pod version from `~> 2.5.0` to `~> 3.1.0` (latest version)

### Fixed
- Fixed CocoaPods version conflict when using alongside Google Mobile Ads SDK which bundles GoogleUserMessagingPlatform 3.x

## [1.0.0] - 2025-01-17

### Initial Release

This is the first release of `community-cordova-plugin-consent`, a standalone fork of the consent module from the original [admob-plus](https://github.com/admob-plus/admob-plus) plugin.

### Credits

A huge thank you to [Ratson](https://github.com/niceonedaviddevs) for creating and maintaining the original admob-plus plugin and its consent module. Due to the original plugin no longer being actively maintained, this standalone repository was created to continue development and provide updates.

### SDK Versions

- **Android**: user-messaging-platform `4.0.0`
- **iOS**: GoogleUserMessagingPlatform `2.5.0`

### Features

- Request consent information update
- Load and show consent form
- Check consent status
- Reset consent state (for testing)
- Full TypeScript support
- iOS and Android support

### Supported Platforms

- Android
- iOS
