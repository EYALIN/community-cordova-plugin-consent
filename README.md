# Community Cordova Plugin Consent

[![NPM version](https://img.shields.io/npm/v/community-cordova-plugin-consent)](https://www.npmjs.com/package/community-cordova-plugin-consent)
[![Downloads](https://img.shields.io/npm/dm/community-cordova-plugin-consent)](https://www.npmjs.com/package/community-cordova-plugin-consent)

Google User Messaging Platform (UMP) SDK plugin for Cordova/Ionic applications. This plugin helps you manage user consent for personalized advertising in compliance with GDPR and other privacy regulations.

## Support This Plugin

I dedicate a considerable amount of my free time to developing and maintaining many Cordova plugins for the community ([See the list with all my maintained plugins][community_plugins]).

To help ensure this plugin is kept updated, new features are added and bugfixes are implemented quickly, please donate a couple of dollars (or a little more if you can stretch) as this will help me to afford to dedicate time to its maintenance.

Please consider donating if you're using this plugin in an app that makes you money, or if you're asking for new features or priority bug fixes. Thank you!

[![Sponsor Me](https://img.shields.io/static/v1?label=Sponsor%20Me&style=for-the-badge&message=%E2%9D%A4&logo=GitHub&color=%23fe8e86)](https://github.com/sponsors/eyalin)

## Credits & Acknowledgments

This plugin was originally forked from [admob-plus](https://github.com/admob-plus/admob-plus) by [Ratson](https://github.com/niceonedaviddevs).

A huge thank you to [Ratson](https://github.com/niceonedaviddevs) for creating and maintaining the original admob-plus plugin and its consent module. The original work laid the foundation for this plugin, and we are grateful for their contributions to the Cordova community.

Due to the original plugin no longer being actively maintained, this standalone repository was created to continue development, provide updates, and ensure compatibility with the latest Google UMP SDK versions.

## Features

- Request consent information update
- Load and show consent form
- Check consent status
- Reset consent state (for testing)
- Full TypeScript support
- iOS and Android support

## Installation

```bash
cordova plugin add community-cordova-plugin-consent
```

Or with Ionic:

```bash
ionic cordova plugin add community-cordova-plugin-consent
```

## SDK Versions

| Platform | SDK | Version |
|----------|-----|---------|
| Android | user-messaging-platform | 4.0.0 |
| iOS | GoogleUserMessagingPlatform | 2.5.0 |

## Basic Usage

### Request Consent Information

```typescript
document.addEventListener('deviceready', async () => {
  // Request consent info update
  await consent.requestInfoUpdate();

  // Check if form is available
  const status = await consent.getFormStatus();

  if (status === consent.FormStatus.Available) {
    // Load and show the form
    await consent.loadForm();
    await consent.showForm();
  }
}, false);
```

### Check Consent Status

```typescript
const consentStatus = await consent.getConsentStatus();

switch (consentStatus) {
  case consent.ConsentStatus.Required:
    // Consent is required but not yet obtained
    break;
  case consent.ConsentStatus.NotRequired:
    // Consent is not required (e.g., user not in EEA)
    break;
  case consent.ConsentStatus.Obtained:
    // User has provided consent
    break;
}
```

### Reset Consent (Testing Only)

```typescript
// Reset consent state for testing
await consent.reset();
```

## Related Plugins

- [community-cordova-plugin-admob](https://github.com/niceonedaviddevs/community-cordova-plugin-admob) - Google AdMob plugin for Cordova

## Contributing

- Star this repository
- Open issue for feature requests
- [Sponsor this project](https://github.com/sponsors/eyalin)

## License

This project is [MIT licensed](LICENSE).

[community_plugins]: https://github.com/niceonedaviddevs?tab=repositories&q=community&type=&language=&sort=
