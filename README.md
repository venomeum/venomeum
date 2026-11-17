# VENOMEUM 🐍✌️

**Venomeum Blockchain — $VMH**

Built by **Venom** ([@venomeum](https://github.com/venomeum)) with **venom.muse**.

> DYOR — don't trust, verify. Not your keys, not your coins.

## 🌐 Website

This repo is also the Venomeum website (GitHub Pages): **https://venomeum.github.io/venomeum/**

## What's in here

| Part | What it is |
| --- | --- |
| `index.html` | The Venomeum website, including a live read-only dashboard for the burner wallet |
| `wallet-tools/` | Python tools that generated and verified the multichain burner wallet (BIP39 → BTC, EVM, Solana, TRON, SUI, TON, NEAR) |
| `wallet/addresses.json` | The burner wallet's **public** addresses only |
| `docs/faucet-plan.md` | The verified testnet faucet research + claim log |
| `assets/` | Venomeum logos |

## 🔥 Burner wallet

One BIP39 mnemonic, eight chains, generated and verified with 27/27 checks
(private keys re-derive to the addresses, sign/verify round-trips on every chain).

**Burner rules:** testnet / faucet / small amounts only. Never significant funds.

## 🚰 Faucet program

Daily automated testnet claims for the burner wallet (Circle USDC/EURC/cirBTC,
SUI, NEAR), every claim verified on-chain before it's reported.
Full research and results: [`docs/faucet-plan.md`](docs/faucet-plan.md).

## ⚠️ Security — read this first

**The wallet backup files (seed phrase + private keys) are NOT in this repo and
must NEVER be committed to GitHub — by anyone, ever.** They live only in private,
offline storage. The `.gitignore` in this repo blocks the backup filenames as a
second line of defence. Anything in this repo is public information only:
code, docs, logos, and public addresses.

## 🗺️ Roadmap (plans, in build)

- On-chain sniper tool + daily transaction activity for the EOA wallet
- Soul-bound NFTs for name services (ENS / BASE.ETH style)
- ERC-20 launches with burnable tax, automatic buyback, automatic liquidity
- Venomeum Blockchain — $VMH
