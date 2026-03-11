# Publishing Your Project

Once your code is prepared and approved, it's time to make it public. This guide covers the practical steps of creating and configuring your open source repository.

## Creating the Repository

### Organization and Naming
- Publish under the [navapbc GitHub organization](https://github.com/navapbc)
- Use clear, descriptive names in lowercase with hyphens (e.g., `strata`, `benefit-delivery-systems`)
- Avoid acronyms unless they're widely understood
- Add a concise description to the repository's About section

### Repository Settings
- Set visibility to **Public**
- Enable **Issues** for bug reports and feature requests
- Enable **Discussions** if you want a space for broader community conversation
- Configure branch protection on `main`:
  - Require pull request reviews
  - Require status checks to pass
  - Prevent force pushes

## Initial Commit Hygiene

### Starting Fresh vs. Preserving History
- **Preserve history** if the commit log is clean and tells a useful story
- **Start fresh** if the history contains secrets, messy commits, or internal references
- If starting fresh, use a single initial commit with a clear message explaining the project's origin

### Before the First Push
- Run a final check for secrets using tools like `git-secrets`, `trufflehog`, or `gitleaks`
- Verify `.gitignore` is comprehensive (IDE files, OS files, build artifacts, environment files)
- Confirm all required files are present

## Setting Up Community Infrastructure

### Issue Templates
Set up `.github/ISSUE_TEMPLATE/` with templates for:
- Bug reports
- Feature requests
- Disable blank issues to guide contributors toward structured templates

### Continuous Integration
- Configure CI to run on pull requests (tests, linting, security scans)
- Use GitHub Actions or your preferred CI platform
- Make CI status visible in the README with badges

### Labels
Create a consistent set of issue labels:
- `bug`, `enhancement`, `documentation`
- `good first issue` — for newcomers to the project
- `help wanted` — for areas where you'd welcome contributions
- `security` — for security-related issues

## Announcement

When the project is ready:

- Share internally at Nava so team members are aware
- Consider a blog post or announcement if the project has broad appeal (see [Writing About Your Project](../promoting/blog.md))
- If relevant, share with the civic tech community

---

**Next**: [Managing Releases](release.md)

**Back to**: [Publishing Open Source](index.md) | [Nava Open Source Guide](../../README.md)
