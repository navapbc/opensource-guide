# Infrastructure and Platform Projects

Infrastructure-as-code, platform tools, and DevOps-oriented projects have specific considerations when being open sourced. These projects often contain configuration details that need careful review before publishing.

## Infrastructure as Code

When open sourcing Terraform modules, Helm charts, or similar IaC:

### Parameterize Everything
- Replace hardcoded values with variables
- Use sensible defaults that work for a general audience
- Document all variables with descriptions and example values

### Remove Environment-Specific Details
- AWS account IDs, Azure subscription IDs, GCP project IDs
- VPC configurations, subnet CIDRs, security group rules specific to your deployment
- Domain names, DNS configurations, and certificate ARNs
- IAM role ARNs and policy attachments specific to your organization

### Provide Examples
- Include example configurations for common deployment scenarios
- Add a `examples/` directory with working example setups
- Document prerequisites (e.g., required cloud provider permissions)

## Dependency Attribution

For projects that bundle or depend on other software:

- Maintain a clear bill of materials for binary dependencies
- Document container base images and their licenses
- Track transitive dependencies and their licenses

## Security Scanning

Infrastructure projects warrant additional security attention:

### Static Analysis
- Run IaC-specific scanners (e.g., `tfsec`, `checkov`, `kics`) before publishing
- Address findings or document accepted risks
- Include scanning in CI for ongoing protection

### Secrets Detection
- Scan for hardcoded credentials, keys, and tokens
- Check for base64-encoded secrets
- Verify no cloud provider credentials are embedded in configuration

### Configuration Security
- Review default security group rules and network policies
- Ensure default configurations follow the principle of least privilege
- Document security-relevant configuration options clearly

## Operational Documentation

Infrastructure projects need more operational context than typical application code:

- **Architecture diagrams**: How components relate to each other
- **Deployment guide**: Step-by-step instructions for deploying the infrastructure
- **Runbook**: Common operational procedures and troubleshooting steps
- **Cost considerations**: Expected cloud resource costs for typical deployments

---

**Back to**: [Launch Considerations](index.md) | [Nava Open Source Guide](../../README.md)
