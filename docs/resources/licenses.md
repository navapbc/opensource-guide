# License Reference

This guide covers Nava's licensing practices and how to choose the right license for your project.

## Nava's Default License

Nava uses **Apache License 2.0** as the default for our open source projects. We chose Apache 2.0 because:

- **Patent grant**: It includes an explicit patent license, protecting users from patent claims
- **Permissive**: It allows broad use, modification, and distribution without copyleft obligations
- **Government-friendly**: It's compatible with most government procurement requirements
- **Industry standard**: It's widely used and well-understood by the open source community
- **Compatible**: It works with most other open source licenses

## Choosing a License

For most Nava projects, Apache 2.0 is the right choice. Consider alternatives only when:

- **Upstream requirements**: If your project is a fork or extension of a copyleft-licensed project, you may need to use the same license
- **Community norms**: Some ecosystems have strong conventions (e.g., MIT is common in JavaScript, GPL in certain Linux tools)
- **Specific goals**: If you want to ensure modifications remain open source, a copyleft license like GPL may be appropriate

### Decision Guide

1. **Default**: Use Apache 2.0
2. **Forking a project?** Use the same license as the upstream project (or a compatible one)
3. **Want copyleft?** Use GPLv3 (compatible with Apache 2.0)
4. **Simple is fine?** MIT is acceptable for small utilities and scripts

## License Text and SPDX Identifiers

When adding a license to your project:

- Include the full license text in a `LICENSE` or `LICENSE.md` file at the repository root
- Use the SPDX identifier in metadata files (e.g., `Apache-2.0`, `MIT`, `GPL-3.0-only`)
- Add license headers to source files where appropriate (see [Preparing Code](../publishing/prepare.md))

### Common SPDX Identifiers

| License | SPDX Identifier |
|---|---|
| Apache License 2.0 | `Apache-2.0` |
| MIT License | `MIT` |
| GNU GPLv3 | `GPL-3.0-only` |
| GNU LGPLv2.1 | `LGPL-2.1-only` |
| Mozilla Public License 2.0 | `MPL-2.0` |
| BSD 2-Clause | `BSD-2-Clause` |
| BSD 3-Clause | `BSD-3-Clause` |

---

**Back to**: [Resources](index.md) | [Nava Open Source Guide](../../README.md)
