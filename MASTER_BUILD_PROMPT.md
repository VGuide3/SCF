# Web3 Transaction Compiler, Relayer & Execution Platform

**MASTER BUILD PROMPT** — Production Web3 infrastructure for smart contract interaction.

## Execution Model

```
PHASE 1: Foundation (Repository, DB, Auth, RBAC)
    ↓ GATE: All tests pass, schema created
PHASE 2: Contract Management (Chains, Contracts, ABI Import)
    ↓ GATE: ABI parser tested, functions displayed
PHASE 3: Compiler (Transaction Specification, script.js generation)
    ↓ GATE: Compilation end-to-end tested
PHASE 4: Direct Wallet Execution (Simulate, Interact, Confirmation)
    ↓ GATE: E2E wallet flow tested on testnet
PHASE 5: Backend Relayer (Worker, Nonce, Queue)
    ↓ GATE: Relayer tested with mock transactions
PHASE 6: Notifications (Telegram, Slack, Alerts)
    ↓ GATE: All notification channels verified
PHASE 7: Security, Testing, Deployment (CI/CD, Docker, Hardening)
    ↓ GATE: All security checks pass
COMPLETE
```

Each phase gates the next. No moving forward until tests pass.

## Core Principles

1. **TransactionSpecification** is the source of truth
2. **No arbitrary code execution** (no eval, no Function())
3. **Blockchain separation**: Compilation ≠ Execution ≠ Observability
4. **Strict TypeScript**, tests for every module
5. **Security first**: No secrets in code, no private keys in frontend

## Technology Stack

- **Frontend**: Next.js, React, TypeScript, TailwindCSS, shadcn/ui
- **Backend**: Node.js, Fastify, PostgreSQL, Prisma, Redis, BullMQ
- **Blockchain**: ethers.js v6
- **Testing**: Vitest, Supertest, Anvil
- **Notifications**: Telegram Bot API, Slack API

## Monorepo Structure

```
/apps
  /web (Next.js dashboard)
  /api (REST API)
  /worker (Transaction execution)
/packages
  /compiler
  /blockchain
  /sdk
  /shared
  /types
/infrastructure
  /docker
  /database
/docs
```

---

See PHASE_1.md to begin.
