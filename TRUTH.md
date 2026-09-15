# SCF: Web3 Transaction Compiler & Relayer Platform

**What it is:** Production-grade Web3 smart contract interaction platform. Users import ABIs, configure contract interactions, compile to transaction specifications, execute via wallet or backend relayer, monitor on-chain with Telegram/Slack alerts.

**Architecture:** 7-phase modular build. Each phase gates the next.

**Current Status:** PHASE 1 - Foundation (Ready to build)

## Phase Checklist

- [ ] **PHASE 1**: Foundation (Monorepo, DB, Auth, RBAC)
- [ ] **PHASE 2**: Contract Management (Chains, ABIs, Explorer)
- [ ] **PHASE 3**: Compiler (Transaction Spec, script.js, Checksum)
- [ ] **PHASE 4**: Direct Wallet (Simulate, Interact, Confirmation)
- [ ] **PHASE 5**: Backend Relayer (Worker, Nonce, Queue, Monitor)
- [ ] **PHASE 6**: Notifications (Telegram, Slack, Alerts)
- [ ] **PHASE 7**: Security & Deployment (CI/CD, Docker, Hardening)

## Run Instructions

```bash
# Local Development
docker-compose up
npm install
npm run db:migrate
npm test

# GitHub Actions (Automated)
# Commit to main → Agent executes current phase
# All tests pass → Agent moves to next phase
```

## NOW → 

Execute PHASE_1 to completion:
1. Build monorepo structure
2. Set up Fastify + Prisma + PostgreSQL
3. Implement auth + RBAC
4. Complete all Phase 1 tests
5. Commit to main with phase summary

---

See `MASTER_BUILD_PROMPT.md` for full architecture.
See `PHASE_1.md` for Phase 1 scope.
