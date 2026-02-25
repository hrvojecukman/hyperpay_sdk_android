# hyperpay_sdk_android

Android AAR artifacts for the HyperPay (OPPWA) Mobile SDK v7.4.0, served via JitPack.

This repository is consumed as a dependency of [`hyperpay_sdk`](https://pub.dev/packages/hyperpay_sdk) and is not intended for direct use.

## Modules

| Module | Artifact |
|---|---|
| `oppwa` | `oppwa.mobile-7.4.0-release.aar` — HyperPay OPPWA Mobile SDK |
| `ipworks3ds` | `ipworks3ds_sdk_9374.aar` — 3DS2 authentication (debug) |
| `ipworks3ds_deploy` | `ipworks3ds_sdk_9374_deploy.aar` — 3DS2 authentication (release) |

## Usage via JitPack

Add JitPack to your repositories:

```gradle
maven { url 'https://jitpack.io' }
```

Then add dependencies:

```gradle
implementation 'com.github.hrvojecukman.hyperpay_sdk_android:oppwa:v7.4.0:oppwa@aar'
debugImplementation 'com.github.hrvojecukman.hyperpay_sdk_android:ipworks3ds:v7.4.0:ipworks3ds@aar'
releaseImplementation 'com.github.hrvojecukman.hyperpay_sdk_android:ipworks3ds_deploy:v7.4.0:ipworks3ds_deploy@aar'
```

## Setup

Before pushing, generate the Gradle wrapper:

```bash
gradle wrapper --gradle-version 8.7
```

Then tag and push:

```bash
git tag v7.4.0
git push origin main --tags
```

JitPack will auto-build on first dependency request.

## License

MIT
