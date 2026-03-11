# Preparing Code for Open Source Release

Before making code public, take the time to ensure it's ready for external eyes. This protects Nava, our clients, and the people who will use the code.

## Code Review for Public Release

Conduct a thorough review specifically focused on public readiness:

### Remove Sensitive Information
- **Secrets and credentials**: API keys, tokens, passwords, connection strings
- **Internal URLs**: References to internal systems, staging environments, VPNs
- **Personal information**: Names, email addresses, or other PII in comments or test data
- **Internal documentation**: References to internal tools, processes, or systems that aren't public

### Check Git History
- Review commit history for accidentally committed secrets
- Consider whether to preserve history or start with a clean initial commit
- Use tools like `git log --all -p` to search for sensitive strings
- If secrets were ever committed, rotate them before publishing regardless of whether you clean the history

### Code Quality
- Remove dead code, commented-out blocks, and TODO items that reference internal work
- Ensure code follows consistent formatting and style
- Add inline comments where the logic isn't self-evident

## Required Files

Every Nava open source project must include:

| File | Purpose |
|---|---|
| `README.md` | Project overview, setup instructions, usage examples |
| `LICENSE` or `LICENSE.md` | Full license text (Apache 2.0 by default) |
| `CONTRIBUTING.md` | How to contribute, code review process |
| `CODE_OF_CONDUCT.md` | Behavioral expectations (Contributor Covenant) |
| `SECURITY.md` | How to report security vulnerabilities |

### README Checklist
A good README for a Nava project includes:

- [ ] Project name and one-line description
- [ ] What problem the project solves
- [ ] Prerequisites and setup instructions
- [ ] Basic usage examples
- [ ] Link to full documentation (if applicable)
- [ ] How to contribute
- [ ] License information

## Copyright and License Headers

Add license headers to source files where appropriate. For Apache 2.0:

```
Copyright [year] Nava PBC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0
```

Not all files need headers — configuration files, data files, and very short files can typically skip them.

## Documentation Standards

- Write documentation for someone who has never seen the project
- Include architecture overviews for complex projects
- Document environment setup and common development tasks
- Keep documentation in the repository alongside the code

## Dependency Audit

Before publishing, audit your dependencies:

- **License compatibility**: Ensure all dependency licenses are compatible with Apache 2.0 (see [License Types](../using/license-types.md))
- **Security vulnerabilities**: Run dependency scanning and resolve known vulnerabilities
- **Necessity**: Remove unused dependencies
- **Pinning**: Consider pinning dependency versions for reproducible builds

---

**Next**: [Getting Approval](approval.md)

**Back to**: [Publishing Open Source](index.md) | [Nava Open Source Guide](../../README.md)
