# hyperpay_sdk_android

Android AAR artifacts for the HyperPay (OPPWA) Mobile SDK v7.11.0, served via JitPack.

This repository is consumed as a dependency of [`hyperpay_sdk`](https://pub.dev/packages/hyperpay_sdk) and is not intended for direct use.

## Modules

| Module | Artifact |
|---|---|
| `oppwa` | `oppwa.mobile-7.11.0-release.aar` — HyperPay OPPWA Mobile SDK |
| `ipworks3ds` | `ipworks3ds_sdk_9625.aar` — 3DS2 authentication (debug) |
| `ipworks3ds_deploy` | `ipworks3ds_sdk_9625_deploy.aar` — 3DS2 authentication (release) |

## Usage via JitPack

Add JitPack to your repositories:

```gradle
maven { url 'https://jitpack.io' }
```

Then add dependencies (the tag is `v<sdkVersion>.<repoRevision>`):

```gradle
implementation 'com.github.hrvojecukman.hyperpay_sdk_android:oppwa:v7.11.0.0:oppwa@aar'
debugImplementation 'com.github.hrvojecukman.hyperpay_sdk_android:ipworks3ds:v7.11.0.0:ipworks3ds@aar'
releaseImplementation 'com.github.hrvojecukman.hyperpay_sdk_android:ipworks3ds_deploy:v7.11.0.0:ipworks3ds_deploy@aar'
```

The OPPWA SDK also needs these transitive dependencies in the consuming module
(see `Android_Frameworks_<version>/dependencies.txt`):

```gradle
implementation 'androidx.appcompat:appcompat:1.7.0'
implementation 'androidx.recyclerview:recyclerview:1.4.0'
implementation 'androidx.browser:browser:1.8.0'
implementation 'androidx.fragment:fragment-ktx:1.8.6'
implementation 'androidx.constraintlayout:constraintlayout:2.2.1'
implementation 'androidx.webkit:webkit:1.13.0'
implementation 'com.google.android.material:material:1.12.0'
implementation 'com.google.code.gson:gson:2.11.0'
implementation 'androidx.lifecycle:lifecycle-viewmodel-ktx:2.8.7'
// Only if PayPal / Venmo (Braintree) brands are enabled — new in 7.11.0:
// implementation 'com.braintreepayments.api:paypal:5.18.0'
// implementation 'com.braintreepayments.api:venmo:5.18.0'
// implementation 'com.braintreepayments.api:data-collector:5.18.0'
```

## Releasing a new SDK version

1. Drop the three AARs from HyperPay's `Android_Frameworks_<version>.zip` into
   `oppwa/libs/`, `ipworks3ds/libs/`, `ipworks3ds_deploy/libs/` (delete the old ones).
2. Update the file names and `version` in each module's `build.gradle`.
3. Commit, then tag and push:

```bash
git tag v7.11.0.0
git push origin main --tags
```

JitPack will auto-build on first dependency request.

## License

MIT
