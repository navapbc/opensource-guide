# Getting Approval to Publish

Before making a project public, ensure you have appropriate review and sign-off. The level of review depends on the project's origin and context.

## Internal Review Process

At minimum, every project needs:

1. **Engineering lead review**: A senior engineer reviews the code for public readiness
2. **Security check**: Verify no secrets, credentials, or sensitive data are present
3. **License verification**: Confirm all dependencies are license-compatible

## Stakeholder Sign-off

Depending on the project's context, you may need additional approval:

### For Government Contract Work
- **Contract review**: Verify the contract's IP terms allow open source release
- **Agency partner alignment**: Ensure the government agency is informed and supportive
- **Data review**: Confirm no sensitive government data, PII, or controlled information is included

### For Internal Tools
- **Business review**: Ensure releasing the tool doesn't compromise Nava's competitive position
- **Dependency check**: Verify no proprietary third-party code is included

## Security Review

The security review should verify:

- No hardcoded credentials, API keys, or tokens in code or git history
- No internal infrastructure details (IP addresses, hostnames, network topology)
- Dependencies are free of known critical vulnerabilities
- The project doesn't expose attack surface for Nava or agency partner systems

## Export Control and Compliance

For government technology projects, consider:

- **Export controls**: Certain cryptographic implementations may have export restrictions
- **ITAR/EAR**: Verify the code doesn't fall under export control regulations
- **Section 508**: If the project includes a user interface, ensure accessibility compliance

## Approval Checklist

Before publishing, confirm:

- [ ] Engineering lead has reviewed and approved
- [ ] No secrets or sensitive data in code or git history
- [ ] All dependency licenses are compatible
- [ ] Government agency partner is informed (if applicable)
- [ ] Contract IP terms allow open source release (if applicable)
- [ ] Required files are in place (README, LICENSE, CONTRIBUTING, CODE_OF_CONDUCT, SECURITY)

---

**Next**: [Publishing Your Project](publish.md)

**Back to**: [Publishing Open Source](index.md) | [Nava Open Source Guide](../../README.md)
