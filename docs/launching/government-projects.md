# Government Technology Projects

Government technology is at the heart of Nava's work — it's how we help people access healthcare, receive benefits, and navigate services that matter in their lives. Open sourcing these projects serves the public interest, but it requires careful attention to the trust our agency partners place in us and the responsibility we carry for the people these systems serve.

## Working in the Open

Nava advocates for developing government technology in the open whenever possible:

- **Start public**: When feasible, create the repository as public from day one rather than open sourcing later
- **Build trust**: Agencies that see development happening transparently are more likely to embrace open source
- **Invite collaboration**: Other agencies, civic tech organizations, and the public can provide valuable feedback

## Partner Considerations

### Agency Alignment
- Work with your government agency partner early to align on the open source approach
- Agencies bring valuable perspective on what can and should be shared publicly — collaborate on those decisions together
- Document the open source approach in project plans and agreements

### Contract Terms
- Review your contract's data rights and IP clauses before publishing
- Federal contracts often have specific clauses (FAR/DFARS) governing software ownership
- Work with Nava's contracts team to understand what's permissible

### Branding and Attribution
- Credit the agency appropriately in the README
- Don't use agency logos or seals without permission
- Be clear about Nava's role as the development partner

## Data Sensitivity

People trust government services with their most personal information. Protecting that trust means being vigilant about what appears in public repositories.

### Protect Personal Data
The following must never appear in public code or configuration — these belong to real people who depend on these services:

- Personally Identifiable Information (PII)
- Protected Health Information (PHI)
- Tax return information
- Social Security numbers or other government identifiers
- Production database credentials or connection strings
- Internal government network details

### Test Data
- Use synthetic or anonymized test data
- Verify test fixtures don't contain real data
- Document how test data was generated

### Configuration
- Use environment variables for all environment-specific configuration
- Provide example configuration files (e.g., `.env.example`) with dummy values
- Never commit `.env` files or similar configuration containing real values

## Compliance Requirements

### Section 508 / Accessibility
Accessible services aren't optional — they're how we make sure everyone can use what we build, regardless of ability.

- If the project includes a user interface, ensure it meets Section 508 and WCAG 2.1 AA standards
- Include accessibility testing in your CI pipeline
- Document accessibility considerations in the README

### FISMA and Security
- Document the project's security controls where relevant
- Follow Nava's security practices for dependency management and vulnerability scanning
- Consider how the open source project fits into the system's Authority to Operate (ATO) boundary

### FedRAMP
- If the project is deployed in a FedRAMP-authorized environment, understand how open sourcing affects the authorization boundary
- Ensure no FedRAMP-sensitive configuration details are published

---

**Back to**: [Launch Considerations](index.md) | [Nava Open Source Guide](../../README.md)
