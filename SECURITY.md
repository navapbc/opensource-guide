# Security Policy

## Overview

The Community Engagement Medicaid platform handles sensitive personal and healthcare information. We take security seriously and have implemented comprehensive security measures to protect user data and system integrity.

## Supported Versions

We provide security updates for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| < Latest| :x:                |

We recommend always using the latest version to ensure you have the most recent security updates.

## Security Architecture

### Infrastructure Security

- **AWS Security**: Built on AWS with security best practices including VPC isolation, security groups, and IAM roles
- **Encryption**: Data encrypted in transit (TLS 1.2+) and at rest (AES-256)
- **Network Security**: Private subnets, NAT gateways, and VPC endpoints for secure communication
- **Database Security**: RDS with encryption, automated backups, and role-based access control
- **Secrets Management**: AWS Secrets Manager for secure credential storage

### Application Security

- **Authentication**: AWS Cognito integration with MFA support
- **Authorization**: Role-based access control using Pundit gem
- **Input Validation**: Comprehensive input sanitization and validation
- **CSRF Protection**: Rails built-in CSRF protection enabled
- **SQL Injection Prevention**: Parameterized queries and ORM usage
- **File Upload Security**: Secure file handling with type validation and virus scanning

### Compliance & Standards

- **HIPAA Compliance**: Designed to support HIPAA compliance requirements
- **NIST Framework**: Follows NIST Cybersecurity Framework guidelines
- **OWASP**: Implements OWASP Top 10 security controls
- **FedRAMP**: Architecture supports FedRAMP compliance requirements

## Security Monitoring

### Automated Security Scanning

- **Container Scanning**: Trivy for container vulnerability scanning
- **Code Analysis**: Static code analysis with security-focused linters
- **Infrastructure Scanning**: Checkov and tfsec for infrastructure security
- **Dependency Scanning**: Automated dependency vulnerability scanning

### Monitoring & Alerting

- **CloudWatch**: Real-time monitoring and alerting
- **Access Logging**: Comprehensive audit trails for all system access
- **Anomaly Detection**: Automated detection of unusual activity patterns
- **Incident Response**: Integrated with incident management systems

## Reporting Security Vulnerabilities

### How to Report

If you discover a security vulnerability, please report it responsibly:

1. **Do NOT** create a public GitHub issue
2. **Do NOT** discuss the vulnerability publicly until it has been addressed

Instead, please report security vulnerabilities by:

- **Email**: Send details to [security@navapbc.com](mailto:security@navapbc.com)
- **Subject Line**: Include "Security Vulnerability - Community Engagement Medicaid"

### What to Include

Please provide as much information as possible:

- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact assessment
- Any suggested fixes or mitigations
- Your contact information for follow-up

### Response Process

1. **Acknowledgment**: We will acknowledge receipt within 24 hours
2. **Initial Assessment**: Initial vulnerability assessment within 72 hours
3. **Investigation**: Thorough investigation and impact analysis
4. **Resolution**: Development and testing of security fixes
5. **Disclosure**: Coordinated disclosure after fixes are deployed

### Timeline Expectations

- **Critical vulnerabilities**: Patches within 24-48 hours
- **High severity**: Patches within 1 week
- **Medium/Low severity**: Patches within 30 days

## Security Best Practices for Contributors

### Development Security

- **Secure Coding**: Follow secure coding practices and OWASP guidelines
- **Dependency Management**: Keep dependencies updated and scan for vulnerabilities
- **Secrets**: Never commit secrets, API keys, or credentials to the repository
- **Code Review**: All code changes require security-focused review
- **Testing**: Include security testing in your test suites

### Environment Security

- **Local Development**: Use secure local development practices
- **Access Control**: Use principle of least privilege for all access
- **Multi-Factor Authentication**: Enable MFA on all accounts
- **Secure Communication**: Use encrypted communication channels

### Infrastructure Security

- **AWS Security**: Follow AWS security best practices
- **Terraform**: Use secure Terraform configurations
- **Container Security**: Build secure container images
- **Network Security**: Implement proper network segmentation

## Security Configuration

### Required Security Settings

For production deployments, ensure:

- TLS 1.2+ for all communications
- Strong password policies in Cognito
- MFA enabled for administrative accounts
- Regular security updates applied
- Monitoring and alerting configured
- Backup and disaster recovery tested

### Security Headers

The application implements security headers including:

- Content Security Policy (CSP)
- HTTP Strict Transport Security (HSTS)
- X-Frame-Options
- X-Content-Type-Options
- X-XSS-Protection

## Incident Response

### Security Incident Classification

- **P0 (Critical)**: Active data breach or system compromise
- **P1 (High)**: Potential data exposure or significant vulnerability
- **P2 (Medium)**: Security weakness requiring attention
- **P3 (Low)**: Minor security improvement opportunity

### Response Team

- **Security Lead**: Primary security contact
- **Engineering Lead**: Technical response coordination
- **Product Lead**: Business impact assessment
- **Legal/Compliance**: Regulatory and legal guidance

### Communication

During security incidents:

- Internal stakeholders notified immediately
- Users notified as required by law and best practices
- Regulatory bodies notified as required
- Public disclosure coordinated appropriately

## Security Training

### For Contributors

- Security awareness training recommended
- Secure coding practices documentation
- Regular security updates and communications
- Access to security tools and resources

### For Users

- Security best practices documentation
- User awareness materials
- Incident reporting procedures
- Regular security communications

## Compliance

### Regulatory Requirements

The platform is designed to support compliance with:

- HIPAA (Health Insurance Portability and Accountability Act)
- State privacy laws and regulations
- Federal information security requirements
- CMS security and privacy requirements

### Audit Support

- Comprehensive audit logging
- Security control documentation
- Regular security assessments
- Compliance reporting capabilities

## Contact Information

For security-related questions or concerns:

- **Security Team**: [security@navapbc.com](mailto:security@navapbc.com)
- **General Support**: See [SUPPORT.md](SUPPORT.md)
- **Emergency Contact**: For critical security incidents requiring immediate attention

## Acknowledgments

We appreciate the security research community and responsible disclosure of vulnerabilities. Contributors who report valid security issues will be acknowledged (with permission) in our security advisories.

---

This security policy is reviewed and updated regularly. Last updated: October 2024
