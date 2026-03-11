# Code Ownership

Code ownership in the context of government technology can be complex. This guide helps Nava team members understand who owns the code they write and what that means for open source.

## Who Owns the Code

### Nava-Authored Code
Code written by Nava employees is generally owned by Nava PBC as a work-for-hire. Nava then licenses this code to the public under an open source license (typically Apache 2.0).

### Government Contract Work
Ownership of code written under government contracts depends on the contract terms:

- **Nava retains copyright** in most cases, while granting the government appropriate usage rights
- **Government ownership** may apply if specified by the contract
- **Joint ownership** is sometimes negotiated

The specific FAR/DFARS clauses in your contract determine the arrangement. Always review these before open sourcing contract work.

### Community Contributions
When external contributors submit code to a Nava project:

- Their contributions are licensed under the project's license (e.g., Apache 2.0)
- The contributor retains copyright on their contribution
- A CLA, if required, clarifies the license grant (see [Accepting Contributions](../accepting/index.md))

## Government Contract Implications

### FAR Data Rights Clauses
Common FAR clauses affecting code ownership:

- **FAR 52.227-14 (Rights in Data - General)**: Default clause for civilian agency contracts
- **DFARS 252.227-7014 (Rights in Technical Data - Noncommercial Items)**: Default for DoD contracts
- **FAR 52.227-17 (Rights in Data - Special Works)**: Government may claim ownership for specially commissioned works

### Practical Considerations
- Understand your contract's data rights before starting development
- If the contract grants the government unlimited rights, Nava can still open source the code (we hold copyright, the government has a license)
- If the contract restricts distribution, consult with Nava's contracts team before publishing

## Maintaining Ownership Records

Good record-keeping supports clear ownership:

- Use consistent copyright notices across all repositories
- Maintain contributor records (GitHub tracks this through commit history)
- Document the relationship between contracts and repositories
- Keep CLA records organized and accessible

---

**Back to**: [Resources](index.md) | [Nava Open Source Guide](../../README.md)
