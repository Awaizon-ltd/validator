# Awarizon Validators

**Run a validator node on the Awarizon blockchain, managed or self-hosted. Secure the network and earn RIZ epoch rewards.**

This is the validator portal: operators apply for or register a node, activate it, and track performance and earnings.

## Features

- **Managed validators:** apply to have Awarizon run a node for you (`/managed`, `/managed/apply`)
- **Self-hosted validators:** register a node you operate yourself (`/self-hosted`, `/self-hosted/register`)
- **Activation:** link and activate a validator with a Polkadot.js-compatible wallet extension (`/activate`)
- **Operator dashboard:** node status, management actions and earnings history with charts (`/dashboard`)
- **Leaderboard:** validator rankings across the network (`/leaderboard`)

## Tech stack

- Next.js (App Router), React and TypeScript
- `@polkadot/extension-dapp` and `@polkadot/util-crypto` for wallet and account handling
- `awarizon.js` for chain access
- MongoDB for applications and registrations
- EmailJS for application emails
- Recharts, Zustand and Tailwind CSS

## Getting started

```bash
git clone https://github.com/Awaizon-ltd/validator.git
cd validator
npm install
cp .env.example .env.local     # fill in the values
npm run dev                    # http://localhost:3000
```

## Environment variables

| Variable | Purpose |
|---|---|
| `NEXT_PUBLIC_RPC_URL` | Awarizon chain RPC endpoint |
| `NEXT_PUBLIC_INDEXER_URL` | Indexer API for validator stats |
| `NEXT_PUBLIC_EXPLORER_URL` | Block explorer, used for links |
| `MONGODB_URI`, `MONGODB_DB` | Application and registration storage |
| `NEXT_PUBLIC_EMAILJS_SERVICE_ID`, `NEXT_PUBLIC_EMAILJS_APPLY_TEMPLATE_ID`, `NEXT_PUBLIC_EMAILJS_PUBLIC_KEY` | Application emails |
| `VALIDATOR_1_MNEMONIC`, `VALIDATOR_2_MNEMONIC` | **Server-only** seeds for the managed validators. Keep them in a secret manager and never commit them. |

## Project structure

```
src/
├── app/
│   ├── managed/  self-hosted/  activate/   # Onboarding flows
│   ├── dashboard/                          # Overview, manage, earnings
│   ├── leaderboard/
│   └── api/                                # activate, validator-application
├── components/  hooks/  lib/  types/
```

## Related

- [awarizon-chain](https://github.com/Awaizon-ltd/awarizon-chain): the Awarizon blockchain
