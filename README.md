# TokenGuard

> Modular on-chain safety oracles for autonomous agents and trading bots.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Live](https://img.shields.io/badge/status-live-brightgreen)](https://tokenguard.net)
[![x402](https://img.shields.io/badge/payment-x402-blue)](https://x402.org)
[![MCP](https://img.shields.io/badge/MCP-compatible-purple)](https://smithery.ai)

**Three oracles. One pricing model. No API key required.**

| Oracle | Chain | Speed | Price |
|--------|-------|-------|-------|
| [PumpGuard](https://tokenguard.net/pump) | Solana · Pump.fun | 312ms avg | $0.02/call |
| [BaseGuard](https://tokenguard.net/base) | Base · ETH · Arbitrum | <1s | $0.02–$0.20/call |
| [WalletGuard](https://tokenguard.net/wallet) | EVM · Any chain | <2s | $0.10/call |

## Why TokenGuard

- **0% of DANGER tokens survive 24 hours** — verified across 50,000+ Pump.fun scans
- **10× better survival rate** on SAFE vs DANGER tokens
- **x402 native** — agents pay automatically in USDC on Base, no API key
- **MCP compatible** — available on Smithery, Glama, and Claude

## Quick Start

```bash
npm install @coinbase/x402-fetch
```

```javascript
import { wrapFetchWithPayment } from '@coinbase/x402-fetch';

const fetch = wrapFetchWithPayment(globalThis.fetch, wallet);

const res = await fetch('https://tokenguard.net/verdict/pump', {
  method: 'POST',
  body: JSON.stringify({ 
    contractAddress: mintAddress, 
    chainId: 'solana' 
  })
});

const { recommendation } = await res.json();
// "SAFE" | "CAUTION" | "AVOID" — $0.02 USDC deducted automatically
```

## Products

### PumpGuard — Pump.fun Safety Oracle
Real-time rug detection for Solana token launches. Checks deployer age, bonding curve reserve, and holder concentration in 312ms.

→ [Try free demo](https://tokenguard.net/pump) · [Docs](https://tokenguard.net/docs)

### BaseGuard — EVM Token Safety
Full verdict on any Base, Ethereum, or Arbitrum token. LP lock status, deployer history, holder analysis.

→ [Try free demo](https://tokenguard.net/base) · [Docs](https://tokenguard.net/docs)

### WalletGuard — Wallet Intelligence
Bot score, rug history, whale classification, mixer detection for any EVM wallet address.

→ [Try free demo](https://tokenguard.net/wallet) · [Docs](https://tokenguard.net/docs)

## Integrations

| Platform | Status |
|----------|--------|
| x402 Protocol | ✅ Live |
| Coinbase AgentKit | ✅ Active |
| Smithery MCP | ✅ Listed |
| Glama | ✅ Listed |
| Virtuals ACP | ✅ Listed |

## The Proof

Every DANGER verdict cross-referenced against DexScreener 24 hours later:

- **0%** of DANGER tokens survive
- **~10%** of SAFE tokens survive
- **10×** better survival rate on SAFE vs DANGER
- **50,000+** Pump.fun launches verified

[Verify any mint on Solscan →](https://solscan.io)

## Documentation

Full API reference, integration guides, and code examples:

**[tokenguard.net/docs](https://tokenguard.net/docs)**

## MCP Server

```bash
npx @smithery/cli install tokenguard
```

[Smithery listing](https://smithery.ai) · [Glama listing](https://glama.ai)

## License

MIT

---

*Built on Base · Solana · Ethereum · Arbitrum · [tokenguard.net](https://tokenguard.net)*
