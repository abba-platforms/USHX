# USHX Deployment Summary – Enterprise Edition

**Project:** US Health Index (USHX)  
**Version:** 1.0  
**Pattern:** UUPS Proxy Upgradeable  
**Deployed by:** Simon Kapenda, Creator  
**Deployed on:** January 26, 2026

---

## 1. Deployment Environment

| Parameter                     | Value                                                                 |
|-------------------------------|-----------------------------------------------------------------------|
| Blockchain Network            | Binance Smart Chain (Mainnet)                                         |
| Chain ID                      | 56                                                                    |
| Hardhat EVM Version           | London                                                                |
| Solidity Compiler             | 0.8.20                                                                |
| Compiler Optimizer            | Enabled, 200 runs, `viaIR: true`                                      |
| Upgrade Framework             | OpenZeppelin Upgrades (UUPS)                                          |
| Node & Package Manager        | Node 20+, npm 10+                                                     |

**Dependencies Installed:**  
- `@openzeppelin/contracts-upgradeable@4.9.6`  
- `@openzeppelin/contracts@4.9.6`  
- `@openzeppelin/hardhat-upgrades`  
- `@chainlink/contracts`  
- `hardhat`  

**Environment Variables Used (.env)**  
- `BSC_RPC` – Mainnet RPC endpoint  
- `PRIVATE_KEY` – Deploying wallet private key  

---

## 2. Pre-Deployment Preparation

1. **Wallet Funded:** Minimum BNB to cover gas fees (>= 0.02 BNB recommended for UUPS proxy).  
2. **Network Configuration:** Configured in `hardhat.config.js` with chainId, gasPrice, and deployer account.  
3. **Contracts Compiled:**  
   ```bash
   npx hardhat clean
   npx hardhat compile
   ```  
   Compiler target: `london`, optimizer enabled, viaIR enabled.  
4. **Contract Verification Plan:** Auto-verification disabled; manual verification planned post-deployment.  

---

## 3. Deployment Script Overview

**Script:** `scripts/deploy.js`  

Key Features:  
- Fetches deployer signer and balance.  
- Logs deployer address and current balance.  
- Deploys `USHX` via OpenZeppelin UUPS proxy using `deployProxy`.  
- Initializes the contract with:  
  - Admin & Treasury addresses  
  - Oracle committee addresses  
  - Initial methodology hash & URI  
  - Guardrail configuration (`MIN_UPDATE_INTERVAL`, `MAX_CHANGE_BPS`)  
  - Smoothing window  
  - Chainlink feed addresses (initialized to zero for now; can be updated)  
  - Weightings for composite pillars  
- Waits for deployment to complete and prints proxy & implementation addresses.  
- Designed for safe UUPS upgrade pattern without a ProxyAdmin (manual upgrades possible).  

---

## 4. Deployment Outputs

| Parameter                | Value                                                                 |
|--------------------------|-----------------------------------------------------------------------|
| Proxy Address            | `0xdffAE6BF5438c3FD93cD1caB8EB36235dcD74032`                          |
| Implementation Address   | `0x13Cc4F30c36bEc991f927C132dC4902C73492648` (Verified)               |
| Upgrade Pattern          | UUPS                                                                  |
| ProxyAdmin               | None (manual upgrade allowed via deployer)                            |
| Auto Verification        | Disabled                                                              |
| Token Name               | `US Health Index`                                                     |
| Token Symbol             | `USHX`                                                                |
| Token Decimals           | `18`                                                                  |
| Deploying Wallet         | `0x228A2BEF1aA95502a8028b8131744C075912f76B`                          |
| Deploying Wallet Balance | 0.010469961 BNB at deployment                                         |

**Deployment Cost:** ~0.01 BNB (~$5.50 USD at the time of deployment).  

---

## 5. Post-Deployment Configuration

1. **Oracle Setup:** Replace temporary zero addresses for Chainlink feeds with live feed addresses.  
2. **Methodology Anchoring:** Verify initial methodology hash and IPFS URI.  
3. **Guardrails:** Confirm `MIN_UPDATE_INTERVAL` and `MAX_CHANGE_BPS` meet operational policy.  
4. **Snapshot Verification:** Ensure initial snapshot exists at version 0.  
5. **Manual Verification:** Recommended to manually verify bytecode on BscScan for audit transparency.  

---

## 6. Upgrade & Maintenance Notes

- **Upgradeable Contract:** UUPS pattern enables future upgrades via deployer-controlled `upgradeTo` function.  
- **ProxyAdmin Omission:** By design, no centralized ProxyAdmin is used; the deployer has upgrade authority.  
- **Future Upgrade Process:**  
  1. Compile new implementation.  
  2. Use OpenZeppelin `upgradeProxy` with the deployed proxy address.  
  3. Verify manually on BscScan.  

---

## 7. Security & Enterprise Considerations

- **Roles & Access Control:**  
  - `DEFAULT_ADMIN_ROLE` – deployer/admin  
  - `ORACLE_ROLE` – oracle committee  
  - `PAUSER_ROLE` – emergency pause  
  - `UPGRADER_ROLE` – upgrade authority (UUPS)  
- **Emergency Controls:**  
  - Pause/unpause  
  - Force index updates  
- **Audit-Friendly:**  
  - Methodology snapshots stored per version  
  - Historical data preserved  
  - Optional moving average smoothing  
- **Gas Efficiency:**  
  - ViaIR compilation  
  - Optimizer enabled  

---

## 8. Recommended Next Steps

1. **Manual Verification:** Confirm deployed proxy & implementation bytecode match local compilation.  
2. **Fund Oracle & Admin Wallets:** Ensure sufficient BNB for future upgrades.  
3. **Integrate Live Chainlink Feeds:** Update contract with real feed addresses.  
4. **Set Guardrails & Methodology Anchoring:** Lock down initial parameters.  
5. **Document Deployment:** Archive this summary in the repository under `/docs/deployment.md`.  

---

## 9. UUPS Proxy Architecture Diagram (ASCII)

```
                             ┌────────────────────┐
                             │      Deployer      │
                             │ 0x228A2BEF1aA95... │
                             └─────────┬────-─────┘
                                       │
                                deploys proxy
                                       │
                                       ▼
                        ┌─────────────────────────────┐
                        │         USHX Proxy          │
                        │ Proxy Storage: admin, impl  │
                        │ Address: 0xdffAE6BF...      │
                        │ Upgradeable via deployer    │
                        └─────────┬───────────────────┘
                                  │
                     ┌────────────┴─────────────┐
                     │                          │
                     ▼                          ▼
            ┌───────────────────┐       ┌───────────────────┐
            │ Implementation    │       │ Proxy Storage     │
            │ USHX v1           │       │ Slots: roles,     │
            │ Address: 0x13Cc4... │     │ state variables   │
            └───────────────────┘       └───────────────────┘
                      │
                      ▼
             ┌───────────────────┐
             │ Chainlink Oracles  │
             │ Roles: ORACLE_ROLE │
             │ Feeds & Aggregates.│
             └───────────────────┘

Notes:
- UUPS pattern allows implementation upgrades without a centralized ProxyAdmin.
- `UPGRADER_ROLE` controls `upgradeTo` function.
- `DEFAULT_ADMIN_ROLE` has emergency and governance privileges.
- Proxy delegates all logic to Implementation while storage remains on Proxy.
```
