# ICO for iOS

An iOS fork of [nathanialf/ico-pc](https://github.com/nathanialf/ico-pc), using its Vulkan renderer through MoltenVK. This fork publishes **iOS builds only**, with version numbers matching the upstream release they are based on.

## Download

[**Download the latest unsigned IPA**](https://github.com/katsifolis/ico-ios/releases/latest/download/ico-pc-ios-unsigned.ipa) · [All iOS releases and checksums](https://github.com/katsifolis/ico-ios/releases)

The current build is based on upstream **v0.5.2**. iOS support is experimental; see the release notes for device feedback and what has been checked.

## Install with LiveContainer

Requires an ARM64 iPhone or iPad running iOS 15 or later and your existing LiveContainer setup.

1. Download the IPA and import it into LiveContainer.
2. Open the guest app's data folder and put your own extracted `ico.o2r` in **Documents**.
3. Launch ICO. Settings, saves and logs are also stored in Documents.

A PAL `Ico_PAL.iso` or `Ico_PAL.chd` can be placed in Documents for first-launch extraction instead. When updating, retain the existing guest's Documents folder so your game data and saves remain available.

**Game data is not included.** You need your own PAL ICO disc (SCES-50760). This community project is not affiliated with Sony or Team Ico. [Legal notes](docs/LEGAL.md).

## Performance on iPhone

Start with **Framerate: 60** and **Resolution: Auto** for adaptive resolution. A fixed 2× resolution renders roughly four times the scene pixels of 1×; the first iOS build was reported to slow down at 2× on iPhone 12. Performance improvements in v0.5.2 have not yet been benchmarked on that phone.

For a performance report, enable this in Documents/ico-pc.ini:

```ini
[dev]
perf_log = true
```

Share the normal log and `Documents/logs/ico-pc-perf.csv`, plus your device, iOS and LiveContainer versions.

## Build and contribute

Build on macOS with Xcode, CMake, Ninja and a macOS host DXC:

```sh
tools/package_ios.sh
```

[Full build instructions](docs/BUILDING.md#iphone-ipa-for-livecontainer) · [Upstream iOS draft PR #42](https://github.com/nathanialf/ico-pc/pull/42)

The `ios-moltenvk` branch carries the iOS implementation and tracks upstream `main`. The `ios` branch supplies this fork's iOS homepage. Releases use upstream version tags such as `v0.5.2` and contain the unsigned IPA and its SHA-256 checksum. The original project provides PC and Android builds on [its own Releases page](https://github.com/nathanialf/ico-pc/releases).

Project license: [MIT](LICENSE). Third-party notices are included in each IPA.
