🇪🇸 [Leer en español](./README.es.md)

# <div align="center">

# Senda

Send what matters. In seconds, wherever you are.

Senda is a conversational AI agent—available in Spanish and English via a simple WhatsApp chat and powered by Stellar USDC—that requires no prior cryptocurrency experience. It allows anyone in Argentina to receive, move, and earn yield on digital dollars without ever leaving the chat.

## What makes this different?

Almost all stablecoin wallets designed for emerging markets require one of two
compromises: handing over control of your funds to the company operating the app, or
handling local currency conversion through a closed, proprietary integration with a single provider—
leaving you with no visibility into what happens to your money while it’s in transit. Senda eliminates both issues. The user's wallet is embedded and self-custodial—the user is the actual cryptographic owner from the very first message, not merely a customer of a custodian. The ARS↔USDC conversion runs on SEP-24—Stellar’s ​​open, standardized protocol for hosted deposits and withdrawals—featuring readable transaction statuses that the AI ​​agent explains to the user in real-time, rather than leaving them waiting for a support response.

| | Senda | Most chat-based stablecoin wallets |
|---|---|---|
| **Custody** | One Stellar account per person, embedded via Privy. Senda does not store the seed phrase; it signs using a session key delegated by the user during onboarding. | Company controls the keys; centralized custody |
| **Fiat settlement** | Open protocol (SEP-24) via a regulated anchor | Closed, proprietary API from a single provider |
| **Fiat off-ramp in Argentina** | Direct to the user's Mercado Pago CVU | Often unresolved |
| **Yield** | Blend v2, lending on Soroban. In Senda, the on-chain position belongs to the treasury, while each individual's share is recorded within Senda. Funds can be withdrawn. | Proprietary financial product; yield engine lacks transparency |
| **Collections** | SEP-7 link. USDC payment is direct. Once sent, the release of funds cannot be made conditional. | Direct and irreversible payment. |
| **Privacy** | Active roadmap toward Confidential Tokens / Stellar Private Payments | Transaction history and balances exposed by default |

## Current Status

Senda is under active development on the Stellar Testnet. In the `senda-backend` repository, the WhatsApp workflow is already functional in code: text and voice notes, balance checks, USDC transfers, SEP-7 payment requests, wallet onboarding, and Blend savings. The SEP-24 bridge points to the test anchor `testanchor.stellar.org`: the bot authenticates via SEP-10, initiates the anchor flow, and provides status updates via WhatsApp. There is no linked Mercado Pago CVU (virtual account). Alfred Pay and Ripio Ramps appear as candidates in the code, not as active clients. Blend v2 is integrated on the testnet: the treasury deposits funds into the pool, and each person's share is recorded in Senda. When a payment is received, the bot offers the option to set aside a portion of the funds. The next milestone identified in the repositories—which has not yet been built—is a pilot program featuring a real-world exit to pesos.

## Repositories

**[`senda-backend`](#)** The product—WhatsApp bot (Cloud API v22), web onboarding (`web-setup`), and Stellar integrations—built in TypeScript. This repository handles SEP-7 for collections, SEP-10 for anchor authentication, SEP-24 for withdrawals, USDC via the Stellar Asset Contract, and Blend v2 yield integration. **[`senda.app`](#)** is the frontend

## Links

- Live app: `[COMPLETE: Actual URL, or bot WhatsApp link — wa.me/...]`
- Documentation: `[COMPLETE: Actual URL, if applicable]`
