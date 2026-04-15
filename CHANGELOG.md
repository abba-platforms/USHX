# Changelog for US Health Index (USHX)

All notable changes to the US Health Index (USHX) are documented in this file.
This includes releases, upgrades, smart contract updates, and documentation changes.

**Project:** US Health Index (USHX)  
**Author:** [Simon Kapenda](https://linkedin.com/in/simonkapenda)  
**Organization:** US Health Index Inc.  
**License:** MIT  
**Start Date:** January 6, 2026

---

## [v1.0.2] - 2026-04-15

### Added

- Introduced USHX Listing & Market Structure Specification document (`USHX-LISTING-SPECS.md`)
- Added README summary section referencing the institutional listing framework
- Defined institutional-grade market formation framework for USHX (US Healthcare Index)
- Established synthetic index classification as a benchmark reference financial instrument
- Implemented controlled supply structure with 5% initial circulating float model
- Introduced structured liquidity formation model based on:
  - capital liquidity (USDT or equivalent)
  - market maker participation
  - staged supply release mechanism
- Defined institutional price discovery framework with controlled early-stage volatility
- Introduced order book architecture model with layered bid/ask liquidity design
- Added governance framework covering:
  - treasury control
  - index methodology oversight
  - market maker constraints
- Defined market integrity and anti-manipulation principles for exchange listing readiness
- Established success metrics based on market quality (spread, depth, stability) rather than speculative volume

### Changed

- Updated README.md to include a structured institutional summary of USHX and a direct reference link to `USHX-LISTING-SPECS.md`

### Notes

- This release formalizes USHX as a benchmark US healthcare index instrument designed for institutional market formation rather than a speculative token listing.
- No changes were made to smart contract logic or on-chain mechanics in this release.

---

## [v1.0.2] — 2026-01-29

### Added
- Public verification of the USHX smart contract on BNB Smart Chain using Hardhat.
- Canonical on-chain reference link to the verified contract on BscScan.
- Improved internal documentation consistency following benchmark analysis standardization.

### Changed
- Renamed `USHX_BENCHMARK_ANALYSIS.md` to `BENCHMARK_ANALYSIS.md` for clarity and long-term maintainability.
- Updated `README.md` to reflect the new benchmark analysis filename.
- Confirmed and documented `evmVersion: "london"` as the standard compiler target for all future deployments.
- Minor documentation refinements for clarity, accuracy, and SEO alignment.

### Fixed
- Resolved proxy verification ambiguity where the block explorer redirected to an already verified implementation.
- General documentation cleanup to ensure consistency across references and links.

---

## [v1.0.1] — 2026-01-19

### Added
- Institutional-grade **Methodology Summary** section in `README.md`.
- Direct backlink from `README.md` to `METHODOLOGY.md` for authoritative index construction rules.
- Clear documentation separation between:
  - Whitepaper (conceptual framework and governance)
  - Benchmark Analysis (comparative and contextual analysis)
  - Methodology (normative index ruleset)

### Changed
- Updated **Benchmark Analysis** to include comparative context with traditional indices.
- Added **NASDAQ-100 market capitalization reference (~USD 33.70 trillion)** for scale benchmarking.
- Clarified the institutional positioning of USHX relative to large-cap global indices.

### Notes
- No changes were made to index methodology, governance framework, or smart contract design in this release.

---

## [v1.0.0] — 2026-01-18

### Added
- **Whitepaper v2.1**: Consolidated whitepaper including:
  - USHX Index Methodology
  - Governance Handbook v1.0
- **BENCHMARK_ANALYSIS.md**:
  - Composite structure
  - Governance framework
  - Token representation
  - Price formation
  - CEX trading considerations
- **README.md**:
  - Links to Whitepaper and Benchmark Analysis
  - Executive summaries for quick reference
  - Repository overview and tags
- **LICENSE**: MIT License.
- **CONTRIBUTING.md**: Contribution and review guidelines.
- **SECURITY.md**: Vulnerability disclosure process, governance controls, and emergency procedures.
- **contracts/USHX_v1_7_Truncated.sol**:
  - Enterprise-grade, audit-ready Solidity contract with IP-protected header.
  - UUPS upgradeability.
  - Oracle committee quorum (3-of-5).
  - Chainlink feed integration across four composite pillars.
  - Snapshotting, smoothing, and methodology anchoring.
  - Guardrails for update intervals and maximum change thresholds.
  - Pausable and role-based access controls.
- Repository structure documented for clarity.
- Social media launch content prepared.
- Commit messages and extended descriptions maintained for all major additions.

### Fixed
- Added explanatory note in contract header regarding omitted sections to protect intellectual property.
- Refined README summaries to eliminate repetition and improve clarity.
- Added consistent backlinks across all core documentation.

### Notes
- This is the initial public release of the US Health Index (USHX) repository and serves as the canonical baseline for all future versions.
