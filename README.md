# ICO for iOS

Community-built, unsigned iPhone and iPad packages of
[nathanialf/ico-pc](https://github.com/nathanialf/ico-pc), using its Vulkan
renderer through MoltenVK. This repository is a home for **iOS downloads
and documentation**. The game data must be supplied separately by the user.

> [!IMPORTANT]
> This is an independent community project. It is **not affiliated with,
> endorsed by, sponsored by, or approved by Sony Interactive Entertainment,
> Sony Computer Entertainment, Sony Group, Team Ico, Apple, or their
> affiliates**. ICO and the other names and trademarks mentioned here belong
> to their respective owners. Their use identifies the game and supported
> platforms; it does not imply an official release or partnership.

## Download

[**Download the latest unsigned IPA**](https://github.com/katsifolis/ico-ios/releases/latest/download/ico-pc-ios-unsigned.ipa)
· [All iOS releases and checksums](https://github.com/katsifolis/ico-ios/releases)

Each release includes a SHA-256 checksum and notes describing its upstream
version, iOS build revision, changes, and known limitations.

iOS support is experimental. Read the release notes before updating.
These packages are intended for an existing LiveContainer setup; they are
not App Store releases and do not include an Apple signing identity.

## What you need

- An ARM64 iPhone or iPad. The app's deployment target is iOS 15 or later;
  your LiveContainer setup may have different requirements.
- A working LiveContainer installation that can run unsigned guest apps.
- Your own legally obtained PAL PlayStation 2 copy of **ICO (SCES-50760)**
  and game files you are legally permitted to extract and use. Other game
  regions and editions are not supported by this port.
- Space for the extracted game archive and, if extracting on the device,
  the disc image as well.

## Install or update

1. Download the IPA from Releases and import it into LiveContainer.
2. Open the ICO guest app's data folder. Put your own extracted `ico.o2r`
   in its **Documents** folder. Alternatively, put your PAL `Ico_PAL.iso`
   or `Ico_PAL.chd` there for extraction on first launch.
3. Launch ICO in landscape. Touch controls and compatible controllers are
   supported.

**Before updating, back up the guest's Documents folder**, especially
`memcard`. Update the existing guest while retaining its data folder.
Deleting the guest or replacing its data folder can remove your saves.
Settings are stored in `config.toml`; normal diagnostic logs are in `logs`.
You do not need to extract your game again if `ico.o2r` is already present.

## Graphics and performance

The port provides options for resolution, frame rate, widescreen, and effects
including fog, glow, depth of field, softening, and motion blur. You can
keep these effects enabled to retain the original game's presentation.
See the upstream [options guide](https://github.com/nathanialf/ico-pc/blob/main/docs/OPTIONS.md).

Start at **1x** for predictable performance, or choose **Auto** to let the
renderer adapt resolution. At 2x, both scene dimensions double: full-screen
rendering covers roughly four times as many pixels, and several effect
buffers also grow. Frame rate and heat depend on the device, scene, settings,
and thermal conditions. No fixed frame rate is guaranteed.

Recent local iOS builds disable benchmark CSV output and detailed performance
logging; internal frame timing remains available for automatic resolution.
The release notes identify which changes are included in each download.

## Updates and bug reports

The default branch contains only this README. The full iOS source checkout
is maintained locally and synced with upstream `main` before builds.
Earlier public source branches, tags, and commit history remain accessible;
this change does not remove previously published source or close the
[upstream iOS draft PR](https://github.com/nathanialf/ico-pc/pull/42).

Releases follow upstream version numbers, such as `v0.5.2`;
additional iOS builds use a separate bundle build revision. Downloads include
the IPA and checksum, without game data. Builds are published when ready;
an upstream commit does not automatically create a new IPA.

For iOS installation or rendering problems, open an issue here with your
device model, iOS and LiveContainer versions, IPA version/build, settings,
and steps to reproduce. Attach a relevant diagnostic log after removing
personal information. **Do not upload disc images, `ico.o2r`, extracted game
assets, or other proprietary files.**

For issues shared with other platforms, see
[upstream issues](https://github.com/nathanialf/ico-pc/issues).

## Credits and licences

- [nathanialf/ico-pc](https://github.com/nathanialf/ico-pc) and its contributors:
  the native port, renderer, game reconstruction, and tooling.
- [ICO decompilation](https://github.com/nathanialf/ico) and its contributors:
  the underlying reconstruction work.
- SDL, MoltenVK, and the other dependency authors: platform and rendering
  support. See upstream
  [third-party notices](https://github.com/nathanialf/ico-pc/blob/main/docs/THIRD_PARTY.md).

The upstream project's MIT licence applies within the scope stated in its
[LICENSE](https://github.com/nathanialf/ico-pc/blob/main/LICENSE). It does not
license ICO's game data, Sony's intellectual property, or third-party
components governed by their own licences. Distributed IPAs retain the
project's `LICENSE` and bundled `NOTICES.txt`; those notices must be
preserved when redistributing the software.

## Legal boundaries

- **No game download is provided.** Releases do not include disc images or
  the extracted `ico.o2r` archive. This project does not provide links to
  unauthorized copies or accept them in contributions or issue attachments.
- **Owning a disc is not blanket permission.** Extraction, copying,
  reverse engineering, and circumvention rules vary by jurisdiction and
  applicable agreements. Use only files and methods you are legally entitled
  to use. Owning the game does not authorize distributing its files.
- **Game rights remain with their owners.** This project makes no ownership
  claim over ICO's artwork, characters, music, dialogue, story, original game
  content, or trademarks. Free distribution and an open-source licence do
  not grant permission to redistribute that content.
- **Software is provided as is**, subject to the applicable licence's warranty
  and liability terms. This README is informational, not legal advice or a
  guarantee that every use or distribution is lawful. The affiliation notice
  does not remove copyright, trademark, or other legal obligations.

Read the upstream [legal notes](https://github.com/nathanialf/ico-pc/blob/main/docs/LEGAL.md).
For a US-specific example of why ownership and backup rights are limited,
see the [US Copyright Office's digital-files FAQ](https://copyright.gov/help/faq/faq-digital.html).
Rightsholders with a concern may contact the maintainer through this
repository's Issues tab, identifying the material and the basis of the
concern without posting private information or proprietary files.
