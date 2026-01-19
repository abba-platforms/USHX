# US Health Index (USHX) Methodology

**Document Status:** Institutional-Grade Procedural Methodology  
**Creator:** Simon Kapenda  
**Version:** 1.1  
**Date:** January 19, 2026  

---

## 1. Purpose

This document defines the **mechanical construction, calculation, and governance rules** of the US Health Index (USHX).  

It serves as the **deterministic rulebook** for:
- Index calculation  
- Data normalization  
- Governance enforcement  
- Token representation  

USHX is a **non-investable, informational benchmark**. This methodology ensures **auditability, repeatability, and transparency**.

---

## 2. Index Architecture

USHX is a **composite, multi-pillar index** representing the U.S. healthcare sector.  

### 2.1 Pillars & Weights

| Pillar | Weight (%) | Data Source |
|--------|------------|-------------|
| Healthcare Equity Performance | 55–65 | S&P 500 Health Care sector (via Chainlink) |
| Healthcare Cost Inflation | 15–20 | CPI Health Sub-index (via Chainlink) |
| Insurance & Services Dynamics | 10–15 | Insurance & Services index (via Chainlink) |
| Innovation Adjustment | 5–10 | R&D / Innovation metrics (via Chainlink) |

**Rules:**
- Sum of weights must always equal 100%.  
- Weights are adjustable only via governance actions.  

---

## 3. Base Index and Normalization

- **Base Value:** 1,000  
- **Base Date:** January 2026  

### Normalization Logic
1. Each pillar is normalized relative to its base period.  
2. Weighted aggregation generates the composite index.  
3. Smoothed values are calculated if `smoothingWindow > 0`:

\[
\text{smoothedIndexValue} = \frac{\text{previousSmoothed} \times (\text{smoothingWindow}-1) + \text{newValue}}{\text{smoothingWindow}}
\]

4. The resulting index level is updated as per **Oracle quorum rules**.

---

## 4. Data Inputs

USHX relies exclusively on **public, verifiable data sources**, ingested on-chain via **Chainlink Aggregator feeds**:

| Feed | Description |
|------|-------------|
| `equityFeed` | S&P 500 Health Care sector |
| `cpiFeed` | Health Sub-index of Consumer Price Index |
| `insuranceFeed` | Insurance & Services index |
| `innovationFeed` | R&D / Innovation indicator |

**Contract Enforcement:**
- Solidity v1.7 ensures **all feeds are positive** and throws if any are invalid.  
- Weighted average computation is deterministic and enforced on-chain.

---

## 5. Index Calculation

### 5.1 Calculation Flow

1. **Oracle Proposal**: Any of the 5 oracles may propose a new index value (`proposeOrApproveIndex`).  
2. **Approval Quorum**: Minimum 3-of-5 approvals required to finalize an update.  
3. **Guardrail Enforcement**:
   - Minimum update interval: `MIN_UPDATE_INTERVAL`  
   - Maximum index change: `MAX_CHANGE_BPS`  
4. **Smoothing**: Applied if `smoothingWindow > 0`.  
5. **Snapshot Storage**: Each finalized update is saved in `versionedSnapshots`.  
6. **Event Emission**: Emits `IndexUpdated` for audit and replication.  

### 5.2 Weighted Aggregation

\[
\text{indexValue} = \frac{\sum (\text{feedPrice} \times \text{weight})}{100}
\]

- Computed via `computeIndexFromFeeds()`  
- On-chain enforcement ensures **non-discretionary computation**.

---

## 6. Governance Rules

### 6.1 Roles

| Role | Solidity Constant | Permissions |
|------|-----------------|------------|
| DEFAULT_ADMIN_ROLE | `DEFAULT_ADMIN_ROLE` | Full administration |
| ORACLE_ROLE | `ORACLE_ROLE` | Propose/approve index updates |
| UPGRADER_ROLE | `UPGRADER_ROLE` | UUPS contract upgrades |
| PAUSER_ROLE | `PAUSER_ROLE` | Emergency pause/unpause |

### 6.2 Governance Procedures

- **Methodology updates** require `DEFAULT_ADMIN_ROLE`.  
- **Oracle replacements** executed via `replaceOracle(index, newOracle)`.  
- **Guardrails update**: `updateGuardrails(newMinInterval, newMaxChangeBps)`.

### 6.3 Conflict & Integrity

- Oracles cannot approve the same proposal twice.  
- Admin cannot renounce DEFAULT_ADMIN_ROLE.  
- Governance logs all actions via events.

---

## 7. Emergency Controls

| Function | Solidity Method | Purpose |
|----------|----------------|---------|
| Pause Index | `pause()` | Emergency stop all transfers & updates |
| Unpause Index | `unpause()` | Resume operations |
| Forced Update | `forceIndexUpdate(newValue)` | Override index deterministically in exceptional cases |

**Notes:**
- Emergency actions are logged on-chain.  
- Index integrity is preserved for historical snapshots.

---

## 8. Upgradeability

USHX uses **UUPS upgradeable pattern**:

- `_authorizeUpgrade(address)` enforces `UPGRADER_ROLE`.  
- `proposeUpgrade(newImplementation)` emits event.  
- Upgrades preserve state and snapshots.

---

## 9. Methodology Anchoring

- Each methodology version has:
  - `methodologyHashes[version]`  
  - `methodologyURIs[version]` (JSON/IPFS reference)  
- Updates require admin approval via `updateMethodologyHash(newHash, newURI)`  
- Index updates reference the current methodology version.

---

## 10. Versioning & Snapshots

- `indexVersion` increments with each finalized update.  
- Snapshots stored in `versionedSnapshots[indexVersion]`  
- Enables auditability, replication, and historical analysis.

---

## 11. Tokenization Notes

- USHX token is **BEP-20, Upgradeable**  
- **Max Supply:** 10,000,000,000 USHX  
- **Token ≠ Index Value**: Token price reflects secondary market dynamics; index is deterministic.

---

## 12. References & Compliance

- Follows IOSCO Principles for Financial Benchmarks  
- Full on-chain **audit trail via events and snapshots**  
- Transparent methodology JSON/IPFS anchored to each version

---

## 13. Contract-to-Methodology Cross-Mapping

| Methodology Clause | Solidity v1.7 Enforcement |
|------------------|---------------------------|
| Pillar weights & normalization | `computeIndexFromFeeds()`, `_calculateWeightedAverage()` |
| Oracle quorum (3-of-5) | `proposeOrApproveIndex()` |
| Snapshot storage | `versionedSnapshots[indexVersion]` |
| Emergency override | `forceIndexUpdate()` |
| Guardrails | `MIN_UPDATE_INTERVAL`, `MAX_CHANGE_BPS` |
| Upgradeability | `_authorizeUpgrade()` / `proposeUpgrade()` |
| Methodology anchoring | `methodologyHashes` / `methodologyURIs` |
| Pausable | `pause()` / `unpause()` |
| Token minting & max supply | `_mint()` / `MAX_SUPPLY` |

This ensures **deterministic execution of the methodology on-chain**.

---

## 14. Version Control

- Methodology document versioning follows semantic versioning (`v1.0`, `v1.1`, …)  
- Solidity contract versions mirror methodology updates  
- Historical versions preserved for transparency and auditability

---

**End of USHX Methodology v1.1**
