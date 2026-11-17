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
| `contracts/` | The $VMH token (tax/burn/buyback), its BuybackBurner sink, the wrapped-native token, and the full deployment record |
| `tokens/vmh.json` | $VMH token metadata (name, symbol, logo, deployments) |
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

## 🪙 $VMH token + Venomeum Swap (live on testnets, 2026-11-18)

**Venomeum (VMH)** — ERC-20, 1B supply. Tax on DEX trades only (wallet-to-wallet
transfers are free): **1% burned**, **1% automatic liquidity**, **1% automatic
buyback** (accrues, auto-swaps to the chain's native token, buys VMH back and
burns it). Neither testnet had a DEX, so we deployed our own Uniswap V2 —
**Venomeum Swap** — and the pools run on it. **Liquidity is removable:** LP
tokens sit in the provider's wallet and can be withdrawn at any time (proven
on-chain — 10% of every pool was withdrawn again after launch).

| Deployment | Contract | Pool pair |
| --- | --- | --- |
| Arc Testnet (burner) | `0xeF8a48269661Fd8d5FE1453A74d27Fe375178cef` | `0x39B3f0294E37C99a2395E443D6795e3B64742FD5` |
| Arc Testnet (Circle agent wallet) | `0x4666CA32A6af759d3dd4752ee1323778854BA6aB` | `0x97573A80f21Ab377D62c340b6C1a6f898133dF98` |
| Robinhood Chain Testnet (burner) | `0xA9808afB0213295778D0CEE459c182C1524858b4` | `0x496d70e4443566c4c94F8F2674e191699166cd21` |

Venomeum Swap (same addresses on both testnets): factory
`0x6e0F7bB0AfA4f4e0208e9A6F06a8759003E2D184`, router
`0xC83d7A0079Fc410Ddd4cE4aaD7bF2216350342Cb`, wrapped native
`0x5Df9ecECC7c0e7b43E7afC3b3238Aa19fB3A0C87`.
Verified end-to-end with real taxed trades: ~2,500 VMH burned per deployment
(tax burns + automatic buyback burns), auto-LP minted to the owner, buyback
fund spent to zero. Full record: [`contracts/deployments.json`](contracts/deployments.json).

## ⚠️ Security — read this first

**The wallet backup files (seed phrase + private keys) are NOT in this repo and
must NEVER be committed to GitHub — by anyone, ever.** They live only in private,
offline storage. The `.gitignore` in this repo blocks the backup filenames as a
second line of defence. Anything in this repo is public information only:
code, docs, logos, and public addresses.

## 🗺️ Roadmap (plans, in build)

- ✅ ERC-20 with burnable tax, automatic buyback, automatic liquidity — $VMH, live on Arc + Robinhood testnets
- ✅ Own Uniswap V2 pools (Venomeum Swap) with removable liquidity
- On-chain sniper tool + daily transaction activity for the EOA wallet
- Soul-bound NFTs for name services (ENS / BASE.ETH style)
- Venomeum Blockchain — the chain itself
