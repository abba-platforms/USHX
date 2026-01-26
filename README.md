<!-- Project Badges -->
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Token Type](https://img.shields.io/badge/Token-BEP--20-blue.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)
![Build](https://img.shields.io/badge/Build-Upgradeable%20UUPS-orange.svg)
![Creator](https://img.shields.io/badge/Creator-Simon%20Kapenda-lightgrey.svg)

# US Health Index (USHX)

## Project Details

**Token Name:** US Health Index  
**Token Symbol:** USHX  
**Token Type:** BEP-20 Upgradeable  
**Total Supply:** 10,000,000,000 USHX  
**Creator:** [Simon Kapenda](https://linkedin.com/in/simonkapenda)  
**Version:** 1.1  
**Date:** January 6, 2026  
**Updated:** January 19, 2026  

---

## USHX Deployment Summary

The **US Health Index (USHX)** token has been deployed on **BSC Mainnet** as a **UUPS upgradeable proxy**. The deployment is fully documented and can be audited for transparency, governance, and upgrade traceability.

Key deployment highlights:

- **Deployer:** Simon Kapenda, Creator  
- **Deployment Date:** January 26, 2026
- **Network:** BNB Smart Chain (BSC) Mainnet     
- **Proxy Address:** `0xdffAE6BF5438c3FD93cD1caB8EB36235dcD74032`  
- **Implementation Address (Verified):** `0x13Cc4F30c36bEc991f927C132dC4902C73492648`  
- **Upgrade Pattern:** UUPS  
- **ProxyAdmin:** NONE (by design)  
- **Auto Verification:** DISABLED  
- **Token Name:** US Health Index (USHX)  
- **Decimals:** 18  

For the **full enterprise-grade deployment record**, including oracle committee setup, Chainlink feed configuration, guardrails, methodology anchoring, and emergency controls, see [DEPLOYMENT.md](./DEPLOYMENT.md).

---

## Executive Summary

**US Health Index (USHX)** is a blockchain-native synthetic benchmark token designed to define and track the economic performance, cost inflation, and structural dynamics of the United States healthcare sector. 

USHX functions as an on-chain reference indicator, providing transparent, rules-based, and auditable exposure to U.S. healthcare macro trends.

**Creator:** Simon Kapenda, founder of US Health Index Inc., and creator of SACE Index (SACE), CillarCoin (CILLAR), and Namibia Digital Dollar (NADD).

USHX does **not** represent ownership of equities, ETFs, derivatives, or any financial instruments. It is a benchmark reference token intended solely for informational, analytical, and integration purposes.

---

## Overview

USHX is designed as an institutional-grade benchmark product, comparable in function (but not legal form or structure) to healthcare indices published by traditional index providers such as S&P, MSCI, or Bloomberg. Unlike off-chain indices, USHX is implemented natively on blockchain infrastructure, enabling programmability, verifiability, and continuous auditability.

The USHX benchmark is methodology-driven, governance-controlled, and designed to support read-only integration by external protocols, analytics platforms, and institutional users.

**Deployment:**

- **Network:** BNB Smart Chain (BSC) Mainnet    
- **Deployment Date:** January 26, 2026  
- **Proxy Address:** `0xdffAE6BF5438c3FD93cD1caB8EB36235dcD74032`  
- **Implementation Address (Verified):** `0x13Cc4F30c36bEc991f927C132dC4902C73492648`  

---

## Whitepaper

The full institutional documentation for US Health Index (USHX), including index methodology, governance framework, legal and benchmark-style disclaimers, smart contract architecture, and contract–whitepaper feature cross-mapping, is available in the official Whitepaper:

**Whitepaper v1.0**  
[View USHX WHITEPAPER.md](https://github.com/abba-platforms/USHX/blob/main/WHITEPAPER.md)

---

## USHX Analysis

**Index Benchmark Analysis:** Provides a full breakdown of USHX’s methodology, composite structure, governance, token representation, price formation, and trading considerations.  
**Analysis:**
[View USHX_BENCHMARK_ANALYSIS.md](https://github.com/abba-platforms/USHX/blob/main/USHX_BENCHMARK_ANALYSIS.md)

---

## Methodology

The **USHX Methodology** defines the formal rules governing index construction, data inputs, weighting logic, rebalancing procedures, governance controls, and integrity safeguards for the US Health Index. It serves as the authoritative specification ensuring transparency, repeatability, and auditability consistent with global benchmark standards.

**Methodology:**   
[View USHX METHODOLOGY.md](https://github.com/abba-platforms/USHX/blob/main/METHODOLOGY.md)

---

## Index Design Summary

USHX is structured as a synthetic composite benchmark reflecting multiple dimensions of the U.S. healthcare sector. The index operates with the following parameters:

- **Base Index Value:** 1,000  
- **Maximum Supply:** 10,000,000,000 USHX  
- **Benchmark Role:** Primary on-chain reference indicator  

### Composite Index Structure (Illustrative)

| Pillar                              | Indicative Weight |
|------------------------------------|-------------------|
| Healthcare equity performance      | 55–65%            |
| Healthcare cost inflation          | 15–20%            |
| Insurance & services dynamics      | 10–15%            |
| Innovation adjustment              | 5–10%             |

Weights are published, rules-based, and adjusted only through governance or scheduled methodology review, as described in the Whitepaper.

---

## Token Characteristics

- **Token Name:** US Health Index  
- **Symbol:** USHX  
- **Token Standard:** BEP-20 (ERC-20 compatible architecture)  
- **Supply Model:** Fixed maximum supply  
- **Function:** Synthetic benchmark reference token  
- **Ownership Rights:** None  

USHX is not a currency, security, commodity, or investment product.

---

## Smart Contract Architecture

The USHX smart contract is implemented using enterprise-grade Solidity architecture and audited open-source components, including:

- OpenZeppelin standard libraries
- UUPS upgradeable proxy architecture
- Explicit admin proxy initialization
- Multi-signature governance with quorum enforcement
- On-chain methodology anchoring via cryptographic hashes
- Role separation, upgrade controls, and emergency pause mechanisms

All contract features are mapped explicitly to Whitepaper clauses.

---

## Governance Framework

USHX governance is designed to align with global benchmark governance standards.

- **Governance Model:** Multi-signature control
- **Quorum Requirement:** 3 of 5 authorized governors
- **Governance Scope:**  
  - Methodology updates  
  - Parameter adjustments  
  - Contract upgrades  
  - Emergency controls  

All governance actions are executed on-chain and are fully auditable.

---

## Network & Deployment Status

- **Target Network:** BNB Smart Chain (BSC) Mainnet  
- **Deployment Status:** Successfully deployed  
- **Planned Deployment:** January 26, 2026  
- **Official Contract Address (Proxy):** `0xdffAE6BF5438c3FD93cD1caB8EB36235dcD74032`  
- **Implementation Address (Verified):** `0x13Cc4F30c36bEc991f927C132dC4902C73492648`      

Only contract addresses published in this repository should be considered official.

---

## Versioning & Upgrade Policy

USHX follows explicit versioning for both methodology and smart contract components:

- **Smart Contracts:** Semantic versioning (e.g., v1.0, v1.1, v1.7)
- **Whitepaper & Methodology:** Independently versioned
- **Upgrades:**  
  - Executed only via governance quorum  
  - Fully on-chain  
  - Backward-compatible where feasible  

Version alignment and upgrade rationale are documented in governance records.

---

## Data Sources & Oracle Disclosure

USHX is a synthetic benchmark derived from public market and macroeconomic data as defined in its methodology.

- The current contract **does not custody funds**
- The current contract **does not pull external oracle feeds**
- Index updates are executed via governance-controlled processes
- Future oracle integrations (e.g., Chainlink) may be introduced only via governance and published methodology updates

---

## Security & Audit Status

- **Audit Status:** Planned prior to mainnet deployment  
- **Audit Scope:** Smart contract architecture, upgrade paths, governance controls  
- **Responsible Disclosure:**  
  Security issues should be reported privately to the maintainers via the contact information published in this repository.

No guarantees are made regarding the absence of vulnerabilities.

---

## Integration Guidance

USHX is intended for **read-only integration** as a benchmark reference.

Permitted uses include:
- Analytics and research platforms
- Protocol-level reference indicators
- Academic and policy research
- Internal institutional benchmarking

USHX is not designed for yield generation, payments, or consumer-facing financial applications.

---

## Risk Factors

Use of USHX involves inherent risks, including but not limited to:

- Methodology change risk  
- Governance and upgrade risk  
- Data representation risk  
- Smart contract risk  
- Network-level risk  

These risks are described in further detail in the Whitepaper.

---

## Repository Structure

```
├── contracts/          # Solidity smart contracts
├── WHITEPAPER.md       # Institutional Whitepaper v1.0
├── README.md           # Project overview
└── LICENSE             # MIT License
```
---

## License

The USHX smart contract codebase is released under the **MIT License**.

The MIT License applies only to the software source code in this repository and does not extend to the US Health Index methodology, benchmark design, index values, trademarks, or branding, which are governed separately as described in the Whitepaper.

---

## Index Publisher & Administrator

US Health Index Inc. acts as the index publisher, methodology administrator, and governance authority for USHX.

---

## Maintainer

US Health Index Inc. (USHX)  
Created January 2026

---

## Legal Notice

USHX is a synthetic benchmark reference token intended solely for informational, analytical, and technological purposes. It does not constitute an offer, solicitation, investment advice, or financial instrument of any kind. Use of USHX is subject to the disclaimers and limitations outlined in the Whitepaper.
