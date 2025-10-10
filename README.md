# Community Engagement Medicaid

A comprehensive platform for managing Medicaid community engagement requirements, built to help states implement and administer work requirements and exemption processes in compliance with federal regulations.

<h1 align="center">
  <img width="300" src="/img/logoname-white.svg#gh-dark-mode-only" alt="infisical">
</h1>
<p align="center">
  <p align="center"><b>The open-source secret management platform</b>: Sync secrets/configs across your team/infrastructure and prevent secret leaks.</p>
</p>

<h4 align="center">
  <a href="https://infisical.com/slack">Slack</a> |
  <a href="https://infisical.com/">Infisical Cloud</a> |
  <a href="https://infisical.com/docs/self-hosting/overview">Self-Hosting</a> |
  <a href="https://infisical.com/docs/documentation/getting-started/introduction">Docs</a> |
  <a href="https://www.infisical.com">Website</a> |
  <a href="https://infisical.com/careers">Hiring (Remote/SF)</a>
</h4>

<h4 align="center">
  <a href="https://github.com/Infisical/infisical/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Infisical is released under the MIT license." />
  </a>
  <a href="https://github.com/infisical/infisical/blob/main/CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen" alt="PRs welcome!" />
  </a>
  <a href="https://github.com/Infisical/infisical/issues">
    <img src="https://img.shields.io/github/commit-activity/m/infisical/infisical" alt="git commit activity" />
  </a>
  <a href="https://cloudsmith.io/~infisical/repos/">
    <img src="https://img.shields.io/badge/Downloads-6.95M-orange" alt="Cloudsmith downloads" />
  </a>
  <a href="https://infisical.com/slack">
    <img src="https://img.shields.io/badge/chat-on%20Slack-blueviolet" alt="Slack community channel" />
  </a>
  <a href="https://twitter.com/infisical">
    <img src="https://img.shields.io/twitter/follow/infisical?label=Follow" alt="Infisical Twitter" />
  </a>
</h4>

<img src="/img/infisical_github_repo2.png" width="100%" alt="Dashboard" />
## 🎯 Overview

This open-source project provides a complete solution for state Medicaid agencies to manage community engagement requirements, including:

- **Activity Reporting**: OSCER (Online Self-Certification of Eligible Requirements) system for beneficiaries to report qualifying activities
- **Exemption Management**: Streamlined process for requesting and processing exemptions from community engagement requirements
- **Income Verification**: Integration with CMS Income Verification as a Service (IVaaS) for automated eligibility verification
- **Case Management**: Staff tools for reviewing applications, managing tasks, and tracking compliance
- **Multi-language Support**: Built-in internationalization with English and Spanish support

## 🏗️ Architecture

The platform consists of:

- **Reporting Application**: Ruby on Rails web application with modern UI using U.S. Web Design System (USWDS)
- **Cloud Infrastructure**: AWS-based infrastructure with Terraform for Infrastructure as Code
- **Security & Compliance**: Built with security best practices and compliance requirements in mind

### Key Technologies

- **Backend**: Ruby on Rails 7.2, PostgreSQL
- **Frontend**: USWDS, ERB templates, JavaScript
- **Infrastructure**: AWS (ECS, RDS, Cognito, S3, SES), Terraform
- **Testing**: RSpec, Playwright (E2E)
- **CI/CD**: GitHub Actions

## 🚀 Quick Start

### Prerequisites

- Docker or Finch (container runtime)
- AWS account with appropriate permissions
- Ruby 3.x (for native development)
- Node.js LTS (for native development)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/navapbc/community-engagement-medicaid.git
   cd community-engagement-medicaid
   ```

2. **Set up environment variables**

   ```bash
   cd reporting-app
   make .env
   # Edit .env file with your configuration
   ```

3. **Run with Docker (Recommended)**

   ```bash
   make init-container
   make start-container
   ```

   Or **run natively**:

   ```bash
   make init-native
   make start-native
   ```

4. **Access the application**
   - Open http://localhost:3000 in your browser
   - Default authentication is set to mock mode for development

### Infrastructure Setup

For production deployment, see our comprehensive [infrastructure documentation](docs/infra/).

```bash
# Set up AWS account and infrastructure
make infra-set-up-account ACCOUNT_NAME=your-account-name
make infra-configure-network NETWORK_NAME=dev
make infra-update-app-build-repository APP_NAME=reporting-app
```

## 📚 Documentation

- **[System Architecture](docs/system-architecture.md)** - High-level system overview
- **[Reporting App Documentation](docs/reporting-app/)** - Detailed application documentation
- **[Infrastructure Guide](docs/infra/)** - Deployment and infrastructure management
- **[Contributing Guidelines](CONTRIBUTING.md)** - How to contribute to the project
- **[Security Policy](SECURITY.md)** - Security practices and reporting

## 🎯 Features

### For Beneficiaries

- **Activity Reporting**: Easy-to-use forms for reporting qualifying community engagement activities
- **Document Upload**: Secure document submission for verification
- **Exemption Requests**: Simple process for requesting exemptions with supporting documentation
- **Multi-language Support**: Available in English and Spanish
- **Mobile-Friendly**: Responsive design works on all devices

### For State Staff

- **Case Management**: Comprehensive tools for reviewing and processing applications
- **Task Management**: Automated workflow management with task assignment
- **Document Review**: Secure access to uploaded documents and supporting materials
- **Reporting Dashboard**: Analytics and reporting capabilities
- **Member Search**: Advanced search and filtering capabilities

### For Administrators

- **User Management**: Role-based access control with AWS Cognito integration
- **System Monitoring**: CloudWatch integration for performance monitoring
- **Audit Trails**: Comprehensive logging and audit capabilities
- **Feature Flags**: Dynamic feature management for controlled rollouts

## 🔧 Development

### Running Tests

```bash
# Ruby/Rails tests
cd reporting-app
bundle exec rspec

# End-to-end tests
make e2e-test APP_NAME=reporting-app BASE_URL=http://localhost:3000

# Infrastructure tests
make infra-test-service APP_NAME=reporting-app
```

### Code Quality

```bash
# Linting
make infra-lint
cd reporting-app && bundle exec rubocop

# Security scanning
trivy fs .
```

## 🌐 Deployment

The project supports multiple deployment environments:

- **Development**: Local development with Docker
- **Staging**: AWS-based staging environment
- **Production**: Full production deployment with monitoring and alerting

See [Infrastructure Documentation](docs/infra/) for detailed deployment instructions.

## 🤝 Contributing

We welcome contributions from the community! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details on:

- Code of conduct
- Development workflow
- Pull request process
- Coding standards

## 📄 License

This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).

## 🆘 Support

- **Documentation**: Check our [comprehensive documentation](docs/)
- **Issues**: Report bugs and request features via [GitHub Issues](https://github.com/navapbc/community-engagement-medicaid/issues)
- **Discussions**: Join community discussions in [GitHub Discussions](https://github.com/navapbc/community-engagement-medicaid/discussions)
- **Security**: Report security vulnerabilities via our [Security Policy](SECURITY.md)

## 🏛️ About

This project is developed by [Nava PBC](https://www.navapbc.com/) in partnership with state Medicaid agencies to improve the administration of community engagement requirements. The platform is designed to be:

- **Accessible**: WCAG 2.1 AA compliant with USWDS components
- **Secure**: Built with security-first principles and regular security assessments
- **Scalable**: Cloud-native architecture supporting high availability and performance
- **Compliant**: Designed to meet federal and state regulatory requirements

---

For more information about Medicaid community engagement requirements and this platform, please visit our [documentation](docs/) or contact the development team.
