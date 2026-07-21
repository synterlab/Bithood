<div align="center">

<img src="https://bithood.xyz/favicon.svg" width="72" alt="Bithood logo" />

# Bithood

**GPU Compute. On-Chain.**

Rent bare-metal H100, A100 & RTX nodes by the second — settled atomically on Solana.  
No sign-up. No credit card. No queues. Just a wallet, a transaction, and an SSH key.

[![Live](https://img.shields.io/badge/Live-bithood.xyz-c8f547?style=flat-square&logo=vercel&logoColor=black)](https://bithood.xyz)
[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?style=flat-square&logo=solana&logoColor=white)](https://solana.com)
[![License](https://img.shields.io/badge/License-MIT-c8f547?style=flat-square)](LICENSE)
[![Built in Public](https://img.shields.io/badge/Built-in%20Public-0a0a0a?style=flat-square&logo=github&logoColor=white)](https://github.com/synterlab/Bithood)
[![Twitter](https://img.shields.io/badge/@bithoodxyz-000000?style=flat-square&logo=x&logoColor=white)](https://twitter.com/bithoodxyz)

</div>

---

## Overview

Bithood is a **decentralized GPU compute marketplace** where node operators list idle capacity and renters pick exactly what they need — priced per second, settled on-chain the moment a session ends.

No invoices. No credit card holds. No support ticket to get access. GPU compute that works like a spot market, not a cloud subscription.

> Started in 2026 out of frustration with how expensive and slow it is to get a GPU when you actually need one.

---

## Features

| | |
|---|---|
| ⚡ **Instant Provisioning** | From transaction confirmation to live SSH in under 90 seconds |
| 🕐 **Second-Level Billing** | Pay only for the exact seconds your GPU is live — on-chain, fully auditable |
| 🌍 **Global Node Network** | 4 continents · 12 regions · deploy compute close to your data |
| 🔒 **Non-Custodial Settlement** | Bithood never holds your funds — smart contracts enforce settlement atomically |
| 🖥️ **Enterprise Hardware** | H100 SXM5 · A100 SXM4/PCIe · RTX 4090 · bare metal with NVLink |
| 📊 **Transparent Market** | Live availability, per-GPU pricing, and regional capacity — visible to everyone |
| 🔑 **No KYC** | Your wallet is your account — no email, no sign-up, no approval |

---

## GPU Catalog

| GPU | VRAM | NVLink | Starting Price |
|-----|------|--------|---------------|
| **H100 SXM5** | 80 GB HBM3 | ✅ Multi-GPU | From $2.49 / hr |
| **A100 SXM4** | 80 GB HBM2e | ✅ Multi-GPU | From $1.29 / hr |
| **A100 PCIe** | 40 GB HBM2 | ❌ | From $0.89 / hr |
| **RTX 4090** | 24 GB GDDR6X | ❌ | From $0.62 / hr |

> Prices reflect live market rates. Actual pricing is determined by node operators and visible on the [live compute feed](https://bithood.xyz).

---

## How It Works

```
 Connect Wallet → Select GPU → Reserve On-Chain → SSH In → Session Ends → Settled
```

**01 — Connect Wallet**  
Connect Phantom, Backpack, or Solflare. No sign-up, no KYC, no waiting for approval.

**02 — Select & Reserve**  
Browse the live compute feed. Pick a GPU tier and reserve capacity in one on-chain transaction.

**03 — SSH & Run**  
Receive SSH credentials instantly. Launch your training job, inference task, or rendering pipeline right away.

**04 — Automatic Settlement**  
Sessions are metered to the second. On-chain settlement fires the moment you disconnect. No surprise invoices.

---

## Quick Start (CLI)

The Bithood CLI handles wallet signing, session management, and SSH key injection. Requires Node 18+.

### Install

```bash
npm install -g @bithood/cli
bithood --version
```

### Authenticate

```bash
# Export keypair from Phantom or Backpack
bithood auth --keypair ~/.config/solana/id.json

# Or use a Ledger hardware wallet
bithood auth --ledger
```

### Browse & Rent

```bash
# List available H100s under $4/hr
bithood markets --tier h100 --max-price 4

# Reserve and get SSH credentials (delivered in < 90s)
bithood rent h100-sxm5-us-east-01
```

### End Session

```bash
# Graceful shutdown — flushes checkpoints before terminating
bithood end --session ses_3kLmXq

# Force-terminate immediately
bithood end --session ses_3kLmXq --force
```

---

## Node Network

12 regions across 4 continents with single-digit millisecond latency to major data centers.

| Region | Location | Avg Latency |
|--------|----------|-------------|
| US East | Virginia | 2 ms |
| US West | Oregon | 5 ms |
| EU Central | Frankfurt | 8 ms |
| EU West | London | 7 ms |
| AP | Singapore | 18 ms |
| AP | Tokyo | 14 ms |
| SA | São Paulo | 22 ms |

---

## Economics

| Party | Take |
|-------|------|
| Node Operators | 95% of session revenue |
| Bithood Protocol | 5% fee per completed session |

Settlement is atomic and on-chain — Bithood never touches operator funds before a session completes.

**Settlement Layer:** Solana Mainnet — sub-second finality at ~$0.00025/tx  
**Hardware Policy:** Bare metal only — no virtualization, no shared memory namespaces, no noisy neighbors

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla JS · HTML · CSS (static, Vite-built) |
| Blockchain | Solana (primary) · Robinhood Chain (EVM) |
| Wallets | Phantom · Backpack · Solflare · MetaMask |
| Deployment | GitHub Pages · Custom domain (bithood.xyz) |
| CLI | Node.js 18+ (`@bithood/cli`) |

---

## Repository Structure

```
Bithood/
├── index.html          # Single-page application (all UI + logic inline)
├── assets/
│   ├── index-*.js      # Bundled JS (Vite output)
│   └── index-*.css     # Bundled CSS (Vite output)
├── favicon.svg         # SVG logo mark
├── og-image.png        # Open Graph preview image (1200×630)
├── robots.txt          # Crawler directives + sitemap reference
├── sitemap.xml         # XML sitemap
├── CNAME               # Custom domain: bithood.xyz
└── .nojekyll           # Disables Jekyll processing on GitHub Pages
```

---

## Deployment

Bithood is deployed via **GitHub Pages** with a custom domain.

```
Production URL : https://bithood.xyz
DNS            : CNAME → synterlab.github.io
TLS            : Enforced via GitHub Pages
```

To deploy changes, push to the `main` branch — GitHub Pages auto-deploys on commit.

---

## Roadmap

- [x] Live compute feed with real pricing
- [x] Wallet-based authentication (Phantom, Backpack, Solflare, MetaMask)
- [x] On-chain session metering & settlement
- [x] CLI (`@bithood/cli`) — install, auth, rent, end
- [x] 12-region global node network
- [ ] Mainnet launch (currently Devnet / Testnet)
- [ ] Multi-GPU workload orchestration (NVLink clusters)
- [ ] Programmatic API (REST + WebSocket)
- [ ] Node operator onboarding portal
- [ ] Mobile wallet support

---

## About

Bithood is an indie project — one builder, one idea, built in public.

GPU compute should work like a spot market, not a cloud subscription. Node operators list idle capacity. Renters pick what they need. Solana settles on-chain the moment a session ends.

Right now Bithood connects **1,200+ GPUs across 12 regions**. The market is live, the billing works, and new node operators join weekly. Everything else is being built in public, one commit at a time.

No team page. No funding announcement. Just working software and a transparent market that gets a little better every week.

---

## Links

| | |
|---|---|
| 🌐 Website | [bithood.xyz](https://bithood.xyz) |
| 🐦 Twitter | [@bithoodxyz](https://twitter.com/bithoodxyz) |
| 📖 Docs | [bithood.xyz/docs](https://bithood.xyz/docs) |
| 📊 Live Markets | [bithood.xyz/#markets](https://bithood.xyz/#markets) |
| 💬 Discord | Coming soon |

---

<div align="center">

© 2026 Bithood · GPU Compute on Solana · [Terms](https://bithood.xyz/terms) · [Privacy](https://bithood.xyz/privacy) · [Status](https://bithood.xyz/status)

</div>
