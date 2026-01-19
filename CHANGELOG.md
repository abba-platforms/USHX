# Changelog for US Health Index (USHX)

All notable changes to US Health Index (USHX) are documented in this file. This includes releases, upgrades, and important updates to the tokenomics and related frameworks.

**Project:** US Health Index      
**Author:** [Simon Kapenda](https://linkedin.com/in/simonkapenda)       
**Organization:** US Health Index Inc.  
**License:** MIT  
**Start Date:** January 6, 2026

---

## [v1.0.1] — 2026-01-19

### Added
- Institutional-grade **Methodology summary section** in `README.md`
- Direct backlink from `README.md` to `METHODOLOGY.md` for authoritative index construction rules
- Clear differentiation between:
  - Whitepaper (conceptual & governance)
  - Benchmark Analysis (comparative & contextual)
  - Methodology (normative index ruleset)

### Documentation
- Improved README navigability and benchmark transparency
- Alignment with professional index publisher disclosure standards (e.g., S&P / MSCI–style documentation separation)

---

### v1.0.1 — 2026-01-19

**Benchmark Analysis Update**

- Updated **USHX Index Benchmark Analysis** to include comparative context with traditional indices
- Added **NASDAQ-100 market capitalization reference (~USD 33.70 trillion)** for scale benchmarking
- Clarified institutional positioning of USHX relative to large-cap global indices
- No changes to index methodology, governance framework, or smart contract design

---

## [1.0.0] - 2026-01-18

### Added
- **Whitepaper v2.1**: Consolidated full Whitepaper including USHX Index Methodology & Governance Handbook v1.0
- **USHX_BENCHMARK_ANALYSIS.md**: Detailed benchmark methodology, composite structure, governance, token representation, price formation, and CEX trading considerations
- **README.md**: 
  - Added links to Whitepaper and Benchmark Analysis
  - Included brief summaries for quick reference
  - Included USHX repo and tags
- **LICENSE**: MIT License added
- **CONTRIBUTION.md**: Guidelines for contributing, code review, and documentation updates
- **SECURITY.md**: Instructions for reporting vulnerabilities, supported versions, security practices, governance, and emergency procedures
- **contracts/USHX_v1_7_Truncated.sol**: Enterprise-grade, audit-ready Solidity contract with IP-protected header, preserving all functional features:
  - UUPS upgradeability
  - Oracle committee quorum 3-of-5
  - Chainlink feed integration for four composite pillars
  - Snapshotting, smoothing, methodology anchoring
  - Guardrails for update interval and max change
  - Pausable and role-based controls
- **Repository structure** documented in README for clarity
- **X / social media content** prepared for launch and airdrop announcements
- **Index summary and benchmark analysis** integrated in README and repository for easy access
- Commit messages and extended descriptions for each major addition maintained in repo

### Fixed / Updated
- Added note in contract header explaining omitted top section to protect IP
- README summaries updated to avoid repetition and provide concise insights for each document
- Backlinks to all relevant documentation (Whitepaper, Benchmark Analysis) added

### Notes
- This is the initial release of the repository with all foundational documents, contracts, and supporting materials for USHX as of January 18, 2026.
