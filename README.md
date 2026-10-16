# SunLedger

An evidence-bounded solar-certificate marketplace prototype for the IEEE ClimateChain Global Hackathon 2026, Renewable Energy & Energy Trading track.

SunLedger will simulate five households, verify signed energy readings under documented uncertainty assumptions, and issue, trade and retire certificates on a local blockchain.

**Current state:** repository layout and planning documents only. No application, contracts, ML model or benchmark has been implemented. There are no install, server or test commands yet; those will be added with the relevant components.

## Project layout

```text
backend/
  domain/          Shared records, registrations and policies
  simulator/       Seeded energy profiles, observations and attacks
  verification/    Standalone physical and uncertainty checks
  ml/              Feature extraction, training and anomaly scoring
  oracle/          Signed certificate-issuance authorizations
  storage/         SQLite persistence and transactional uniqueness
  api/             FastAPI routes and orchestration
  tests/           Backend tests and shared fixtures
contracts/
  contracts/       Solidity registry, marketplace and test payment token
  scripts/         Local deployment and seed scripts
  test/            Hardhat contract tests
frontend/
  src/
    views/         Neighborhood, verification, marketplace and demo views
    lib/           API, wallet and contract adapters
  tests/           Browser integration tests
benchmarks/
  config/          Frozen evaluation configurations
  results/         Selected reproducible reports
  tests/           Scenario and metric checks
datasets/          Optional documented historical inputs
docs/              Architecture, build plan and historical exploration
```

Empty non-Python directories contain `.gitkeep` files so Git preserves the layout. Python modules contain package documentation only. This scaffold does not establish dependency versions or complete the plan's interface/setup milestone.

## Design and build approach

- [Architecture](docs/architecture.md): components, shared records, verification, trust boundaries and certificate lifecycle.
- [Build plan](docs/plans/2026-10-16-2128-feat-sunledger-mvp-plan.md): phased implementation, dependencies and acceptance gates.
- [Document index](docs/README.md): active documents and earlier exploration.

The first implementation milestone is shared interfaces followed by the simulator and standalone deterministic Proof-of-Surplus verifier. Dependencies and setup commands will be pinned before implementing those components.

## Scope

All electricity and payments are simulated. Certificates are not official renewable-energy certificates. Trading a certificate does not route physical electricity, establish external environmental entitlement or prove carbon savings.
