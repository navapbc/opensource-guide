# Managing Releases

Publishing your project is just the beginning. Ongoing release management ensures your project stays healthy, secure, and useful to its community.

## Versioning

Use [Semantic Versioning](https://semver.org/) (SemVer) for releases:

- **MAJOR** (1.0.0 → 2.0.0): Breaking changes that require users to update their code
- **MINOR** (1.0.0 → 1.1.0): New features that are backward-compatible
- **PATCH** (1.0.0 → 1.0.1): Bug fixes and minor improvements

For pre-1.0 projects, the API is considered unstable and breaking changes can happen in minor versions.

## Changelog Practices

Maintain a `CHANGELOG.md` in the repository root:

- Organize entries by version and date
- Group changes by type: Added, Changed, Deprecated, Removed, Fixed, Security
- Write entries from the user's perspective — what changed for them?
- Link each version to the corresponding git tag or comparison

Follow the [Keep a Changelog](https://keepachangelog.com/) format for consistency.

## Release Process

For each release:

1. **Update the changelog** with all changes since the last release
2. **Update the version** number in relevant files (package.json, setup.py, etc.)
3. **Create a git tag** matching the version (e.g., `v1.2.0`)
4. **Create a GitHub Release** with release notes summarizing the changes
5. **Publish artifacts** if applicable (npm packages, PyPI packages, Docker images)

## Long-term Maintenance

### Maintenance Commitments
Be honest with your community about your maintenance capacity:

- If the project is actively developed, say so
- If it's in maintenance mode (bug fixes only), communicate that
- If maintenance will end, give advance notice and consider transferring ownership

### Security Updates
- Monitor dependencies for known vulnerabilities
- Prioritize security patches — they should be released promptly
- Follow the process in [SECURITY.md](../../SECURITY.md) for handling vulnerability reports

### Deprecation
When deprecating features or the entire project:

- Announce deprecation clearly in the README and CHANGELOG
- Provide a migration path or alternative when possible
- Keep the repository available (archive rather than delete)
- Set a clear timeline for end of support

---

**Back to**: [Publishing Open Source](index.md) | [Nava Open Source Guide](../../README.md)
