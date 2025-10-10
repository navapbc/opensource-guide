# Contributing to Community Engagement Medicaid

Thank you for your interest in contributing to the Community Engagement Medicaid platform! This project helps state Medicaid agencies manage community engagement requirements, and we welcome contributions from developers, designers, policy experts, and community members.

## 🎯 Ways to Contribute

### Code Contributions
- Bug fixes and feature improvements
- New features and enhancements
- Performance optimizations
- Security improvements
- Documentation updates

### Non-Code Contributions
- Bug reports and feature requests
- Documentation improvements
- User experience feedback
- Accessibility testing
- Translation and localization
- Community support and discussions

## 🚀 Getting Started

### Prerequisites

Before contributing, ensure you have:

- Git installed and configured
- Docker or Finch (container runtime)
- Basic familiarity with Ruby on Rails (for backend contributions)
- Understanding of AWS services (for infrastructure contributions)
- Familiarity with U.S. Web Design System (for frontend contributions)

### Development Setup

1. **Fork and Clone**
   ```bash
   # Fork the repository on GitHub, then clone your fork
   git clone https://github.com/YOUR-USERNAME/community-engagement-medicaid.git
   cd community-engagement-medicaid
   ```

2. **Set Up Development Environment**
   ```bash
   cd reporting-app
   make .env
   # Edit .env file with development configuration
   make init-container  # or init-native for local development
   ```

3. **Start Development Server**
   ```bash
   make start-container  # or start-native
   # Application available at http://localhost:3000
   ```

4. **Run Tests**
   ```bash
   # Ruby/Rails tests
   cd reporting-app && bundle exec rspec
   
   # End-to-end tests
   make e2e-test APP_NAME=reporting-app BASE_URL=http://localhost:3000
   
   # Infrastructure tests
   make infra-test-service APP_NAME=reporting-app
   ```

## 📋 Development Workflow

### 1. Choose an Issue

- Browse [open issues](https://github.com/navapbc/community-engagement-medicaid/issues)
- Look for issues labeled `good first issue` for newcomers
- Comment on the issue to indicate you're working on it
- Ask questions if you need clarification

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 3. Make Changes

- Follow our coding standards (see below)
- Write tests for new functionality
- Update documentation as needed
- Ensure accessibility compliance
- Test your changes thoroughly

### 4. Commit Changes

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```bash
git commit -m "feat: add new activity reporting feature"
git commit -m "fix: resolve authentication redirect issue"
git commit -m "docs: update API documentation"
```

### 5. Push and Create Pull Request

```bash
git push origin your-branch-name
```

Then create a pull request on GitHub with:
- Clear title and description
- Reference to related issues
- Screenshots for UI changes
- Test results and coverage

## 🎨 Coding Standards

### Ruby/Rails Standards

- Follow [Ruby Style Guide](https://rubystyle.guide/)
- Use RuboCop for linting: `bundle exec rubocop`
- Write descriptive method and variable names
- Include RSpec tests for all new functionality
- Follow Rails conventions and best practices

### Frontend Standards

- Use U.S. Web Design System (USWDS) components
- Ensure WCAG 2.1 AA accessibility compliance
- Write semantic HTML
- Follow progressive enhancement principles
- Test across different browsers and devices

### Infrastructure Standards

- Use Terraform for all infrastructure changes
- Follow AWS security best practices
- Document infrastructure changes thoroughly
- Test infrastructure changes in isolated environments
- Use meaningful resource names and tags

### General Standards

- Write clear, concise commit messages
- Include comprehensive tests
- Update documentation for new features
- Follow security best practices
- Ensure backwards compatibility when possible

## 🧪 Testing Guidelines

### Unit Tests

- Write tests for all new functionality
- Maintain or improve test coverage
- Use descriptive test names
- Test both happy path and edge cases

### Integration Tests

- Test complete user workflows
- Verify API integrations
- Test authentication and authorization
- Validate data persistence

### End-to-End Tests

- Test critical user journeys
- Verify cross-browser compatibility
- Test accessibility features
- Validate mobile responsiveness

### Security Testing

- Test authentication and authorization
- Validate input sanitization
- Check for common vulnerabilities
- Test file upload security

## 📚 Documentation

### Code Documentation

- Document complex algorithms and business logic
- Include inline comments for non-obvious code
- Update README files for significant changes
- Document API endpoints and parameters

### User Documentation

- Update user guides for new features
- Include screenshots for UI changes
- Write clear, step-by-step instructions
- Consider multiple user personas

### Technical Documentation

- Document architecture decisions
- Update deployment guides
- Include troubleshooting information
- Document configuration options

## 🔍 Code Review Process

### Submitting for Review

- Ensure all tests pass
- Update documentation
- Self-review your changes
- Request review from appropriate team members

### Review Criteria

Reviewers will check for:

- **Functionality**: Does the code work as intended?
- **Security**: Are there any security vulnerabilities?
- **Performance**: Will this impact system performance?
- **Accessibility**: Does this maintain accessibility standards?
- **Maintainability**: Is the code readable and maintainable?
- **Testing**: Are there adequate tests?

### Addressing Feedback

- Respond promptly to review comments
- Make requested changes or discuss alternatives
- Update tests and documentation as needed
- Re-request review after making changes

## 🚨 Security Considerations

### Secure Development

- Never commit secrets or credentials
- Validate all user inputs
- Use parameterized queries
- Implement proper authentication and authorization
- Follow OWASP security guidelines

### Reporting Security Issues

- Do NOT create public issues for security vulnerabilities
- Report security issues to [security@navapbc.com](mailto:security@navapbc.com)
- See [SECURITY.md](SECURITY.md) for detailed reporting process

## 🌐 Accessibility Requirements

### WCAG 2.1 AA Compliance

- Use semantic HTML elements
- Provide alternative text for images
- Ensure keyboard navigation works
- Maintain sufficient color contrast
- Test with screen readers

### Testing Accessibility

- Use automated accessibility testing tools
- Test with keyboard-only navigation
- Verify screen reader compatibility
- Check color contrast ratios
- Test with users who have disabilities

## 🌍 Internationalization

### Adding New Languages

- Use Rails i18n framework
- Add translations to appropriate locale files
- Test with different text lengths
- Consider right-to-left languages
- Validate date and number formatting

### Translation Guidelines

- Use clear, simple language
- Avoid technical jargon
- Consider cultural context
- Test translations with native speakers
- Maintain consistency across the application

## 📞 Getting Help

### Community Support

- **GitHub Discussions**: Ask questions and share ideas
- **GitHub Issues**: Report bugs and request features
- **Documentation**: Check existing documentation first

### Direct Contact

- **General Questions**: Create a GitHub discussion
- **Bug Reports**: Create a GitHub issue
- **Security Issues**: Email [security@navapbc.com](mailto:security@navapbc.com)
- **Contribution Questions**: Comment on relevant issues

## 🏛️ Legal and Licensing

### Contributor License Agreement

By contributing to this project, you agree that:

- Your contributions are your original work
- You have the right to submit your contributions
- Your contributions are released under the project's license
- You understand this is a public domain project (CC0 1.0)

### Code of Conduct

All contributors must follow our [Code of Conduct](CODE_OF_CONDUCT.md). We are committed to providing a welcoming and inclusive environment for all contributors.

## 🎉 Recognition

### Contributors

- All contributors are recognized in our contributor list
- Significant contributions may be highlighted in release notes
- We appreciate all forms of contribution, not just code

### Maintainers

Current maintainers:
- Nava PBC Engineering Team
- State agency partners
- Community maintainers

## 📈 Project Roadmap

### Current Priorities

- Enhanced accessibility features
- Performance optimizations
- Additional language support
- Improved mobile experience
- Enhanced security features

### Future Goals

- API improvements
- Advanced reporting features
- Integration with additional state systems
- Enhanced user experience
- Expanded documentation

## 🔄 Release Process

### Versioning

We follow [Semantic Versioning](https://semver.org/):
- **Major**: Breaking changes
- **Minor**: New features (backwards compatible)
- **Patch**: Bug fixes (backwards compatible)

### Release Schedule

- Regular releases every 2-4 weeks
- Security patches released as needed
- Major releases announced in advance

---

Thank you for contributing to the Community Engagement Medicaid platform! Your contributions help improve healthcare access and administration for millions of Americans.
