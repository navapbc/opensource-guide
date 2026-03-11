# Using Open Source Software

The services we build help people access healthcare, receive benefits, and navigate government programs. Open source software helps us deliver those services faster, more transparently, and with the kind of resilience that government systems demand. By building on community-maintained tools, we reduce duplication across agencies and focus our energy where it matters most — the people we serve.

This section covers how to evaluate, adopt, and use open source software at Nava.

## Why Open Source Matters at Nava

Open source aligns directly with Nava's mission to make government services simple and effective:

- **Transparency**: The public should be able to inspect the technology that serves them
- **Collaboration**: Shared foundations accelerate progress across agencies, so improvements in one program benefit others
- **Quality**: Widely-used open source projects benefit from broad peer review and testing
- **Cost-effectiveness**: Reducing duplication means more resources go toward outcomes for people
- **Sustainability**: Community-maintained projects build lasting capacity that outlives individual contracts

## Evaluating Open Source Projects

Before adopting an open source dependency, evaluate it across these dimensions:

### Community Health
- Is the project actively maintained? Look at commit frequency, issue response times, and release cadence
- Does it have multiple contributors, or is it a single-maintainer project?
- Is there a welcoming community with a code of conduct?

### Technical Fit
- Does it solve your specific problem without excessive complexity?
- Is it well-documented with clear examples?
- Does it have a reasonable test suite?
- What is its dependency footprint?

### License Compatibility
- Is the license compatible with Apache 2.0 (Nava's default license)?
- Are there copyleft obligations that could affect your project?
- See [Understanding License Types](license-types.md) for detailed guidance

### Security Posture
- Does the project have a security policy and vulnerability reporting process?
- Are known vulnerabilities tracked and patched promptly?
- Is it included in security advisory databases?

## Government-Specific Considerations

Government services handle sensitive data and serve people who depend on their reliability. When using open source in these projects, keep these factors in mind:

- **Authority to Operate (ATO)**: Open source dependencies are part of your system's security boundary and must be documented in ATO packages
- **Supply chain security**: Use dependency scanning tools to identify and track vulnerabilities — the people who use these services are counting on us
- **Compliance requirements**: Ensure dependencies don't introduce compliance issues (e.g., ITAR-restricted cryptography)
- **Data handling**: Verify that dependencies don't transmit data to third parties — protecting the privacy of the people we serve

## Getting Help

If you're unsure about whether to use a particular open source project, reach out to your engineering lead or the open source team — we're happy to help think through license compatibility, security posture, and technical fit.

---

**Next**: [Understanding License Types](license-types.md)

**Back to**: [Nava Open Source Guide](../../README.md)
