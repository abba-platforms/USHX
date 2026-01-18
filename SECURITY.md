# Security Policy for US Health Index (USHX) Repository

## Reporting a Vulnerability

If you discover a security vulnerability in USHX, please report it **privately** to the core team:

- **Email:** security@ushxtoken.com (or an official contact if preferred)
- Include as much detail as possible, including:
  - Steps to reproduce
  - Impact assessment
  - Affected files, contracts, or components
  - Suggested mitigation if available

Do **not** create a public issue for security vulnerabilities.

---

## Supported Versions

Security patches and updates are only guaranteed for the **latest stable release** of:

- USHX Smart Contracts (BEP-20, ERC-20 compliant)
- USHX Benchmark Analysis methodology code
- Repository documentation relevant to token governance and index logic

Legacy versions may not receive active monitoring.

---

## Security Practices

The USHX project follows these security best practices:

1. **Upgradeable Contracts**
   - All contracts use UUPS proxy patterns for controlled, auditable upgrades
2. **OpenZeppelin Standards**
   - Contracts implement OpenZeppelin audited libraries and best practices
3. **Code Review & Testing**
   - All pull requests require peer review
   - Comprehensive unit testing is mandatory for all code changes
4. **Audit-Ready**
   - The codebase is structured to facilitate third-party security audits
5. **Governance Checks**
   - Index methodology and critical parameter changes are subject to quorum approval (3 of 5)

---

## Reporting Timeline

- The USHX core team will acknowledge receipt of a security report within **48 hours**.
- Critical vulnerabilities will be addressed immediately.
- Public disclosure will be coordinated with the reporter after a fix is verified.

---

## Safe Contribution Guidelines

- Avoid including sensitive keys, credentials, or access tokens in any pull request.
- Follow best practices for smart contract security, including input validation and fallback protections.
- Document all changes clearly for auditability.

---

## License and Liability

USHX is provided under the **MIT License**. Reporting a vulnerability does not create any contractual or financial obligations on the core team beyond fixing the issue.  

---

Thank you for helping keep USHX secure and reliable.
