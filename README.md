# Percolator Vision

![Percolator Vision](public/brand/percolator-vision-logo.png)

**Real-time intelligence for the Percolator perpetual futures ecosystem on Solana.**

---

## The Thesis

Percolator is a permissionless perpetuals protocol. Anyone can fork it, anyone can deploy a market, anyone can LP. That's the power — and the problem. Liquidity is fragmenting across forks, risk is invisible, and traders have no single place to see what's actually happening.

**Percolator Vision is the Bloomberg Terminal for the Percolator ecosystem.** Read-only, real-time, on-chain-native. No trading, no custody, no middleman — just ground truth.

---

## What It Does

A live dashboard that streams the state of every Percolator market in the ecosystem directly from Solana. Positions, liquidations, LP health, insurance fund solvency, whale flow, network-wide risk — all updating the moment the chain updates.

**Two surfaces:**

- **Dashboard** — per-market deep dive with 5 analytics tabs plus a fully customizable workspace grid
- **Scanner** — paste any Solana program ID, we verify the `PERCOLAT` magic bytes on-chain and surface the full market structure

---

## Core Features

### Real-Time Market Intelligence
- **Position Map** — every open position rendered as a bubble, sized by collateral, colored by direction, updating live
- **Liquidation Heatmap** — see where liquidations cluster, who's next, and how far the price has to move
- **Whale Tracker** — largest positions by collateral, ranked by unrealized PnL and distance-to-liquidation
- **Position Flow** — deltas between snapshots: new opens, closes, size changes, net directional bias
- **Market Pulse** — aggregate health signal combining OI balance, funding, and activity

### Ecosystem-Wide View
- **Cross-Market Overview** — every market in every program on one screen
- **All Programs Overview** — aggregate TVL, OI, user counts, and health across the entire ecosystem
- **Network Health Score** — a single 0-100 grade combining five components: Insurance (30), LP Coverage (25), OI Balance (20), Activity (15), Solvency (10)

### AI-Powered Briefings
- **Per-Market AI Insights** — Claude generates a written analysis of each market's risk profile, positioning, and notable movements
- **Ecosystem AI Insights** — synthesized view across every program
- **Grid Agent Chat** — conversational interface to the entire Percolator ecosystem, registered on ClawGrid (Dialect Blinks)

### Fork Discovery
- **Program Scanner** — validate any Solana program ID against the Percolator slab layout; valid forks are auto-persisted
- **Auto-Discovered Programs** — non-curated forks appear in a dedicated sidebar with green accent and freshness badges
- **Stale Detection** — forks that fail re-validation are flagged so you know what's still live

### Trader Tools
- **Workspace Grid** — drag, resize, and save your own layout of any 20+ panels; three presets out of the box (Default, Trader Focus, Risk Monitor)
- **Three Themes** — Dark, Mono, and Terminal
- **Deep Links** — every program and market has a shareable URL
- **DeFi Safety Checklist** — source-available, formal verification, upgrade policy, bug bounty, emergency halt — per program

---

## Real-Time Architecture

Percolator Vision is **WebSocket-first**. Every visible market subscribes to its on-chain slab account via Solana's account-change subscription. When the chain updates, the UI updates — no polling delay.

- **Primary**: WebSocket streaming via `onAccountChange`, parsed from raw slab bytes with zero server round-trips
- **Fallback**: automatic degradation to HTTP polling if the WebSocket drops
- **No database**: every number you see is parsed live from on-chain data

---

## Supported Programs

| Program | Network | Status |
|---|---|---|
| Meme Liquid | mainnet | Live — 9 markets |
| Percolator | devnet | Coming Soon |
| Alienator | devnet | Coming Soon |
| perply | devnet | Coming Soon |
| PERC | devnet | Coming Soon |

Plus every community fork surfaced by the scanner.

---

## $VISION Token

$VISION is the access token for the Percolator Vision intelligence layer. Holders unlock AI-powered market briefings and premium analytics.

- **Contract**: `8646cVbPJsj7eMEhbUhA1am21c1E4r7pCrRqxrngBAGS`
- **Supply**: 1,000,000,000
- **Access Gate**: 50,000 $VISION unlocks AI briefings
- **Fee Strategy**: every $500 in bags.fm trading fees earned is converted to 1 SOL of permanent liquidity locked on Meteora (community-voted pivot from burn to LP after 7 burns and >1% of supply destroyed)

---

## Who It's For

- **Traders** — see where risk is concentrated before it moves the market
- **LPs** — monitor utilization, insurance coverage, and solvency across every pool you back
- **Researchers** — a canonical dataset of the Percolator ecosystem in one place
- **Protocol teams** — benchmark your deployment against the rest of the ecosystem

---

## Status

Live on mainnet. Tracking 9 markets across Meme Liquid today, with four more programs preparing launch on devnet. New forks are auto-discovered as they deploy.

---

## License

MIT
