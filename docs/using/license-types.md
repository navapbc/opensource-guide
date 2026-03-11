# Understanding License Types

Choosing and using open source software requires understanding the licenses that govern it. This guide covers the major license categories and their implications for Nava projects.

## Permissive Licenses

Permissive licenses impose minimal restrictions on how software can be used, modified, and distributed. These are generally the easiest to work with.

### MIT License
- One of the simplest and most common licenses
- Requires only attribution (include the copyright notice)
- Compatible with virtually all other licenses

### BSD Licenses (2-Clause and 3-Clause)
- Similar to MIT with minor variations
- 3-Clause adds a non-endorsement clause
- Broadly compatible with other licenses

### Apache License 2.0
- Nava's default license for our own projects
- Includes an explicit patent grant (protects users from patent claims)
- Requires attribution and notice of changes
- Compatible with GPLv3 but not GPLv2

## Copyleft Licenses

Copyleft licenses require that derivative works be distributed under the same or compatible license terms. This has implications for how you integrate the software.

### GNU General Public License (GPL)
- **GPLv2**: Requires derivative works to be licensed under GPLv2. Not compatible with Apache 2.0
- **GPLv3**: Requires derivative works to be licensed under GPLv3 or later. Compatible with Apache 2.0
- Linking to GPL libraries may make your project a derivative work

### GNU Lesser General Public License (LGPL)
- Allows linking to LGPL libraries without your project becoming a derivative work
- Modifications to the LGPL library itself must be shared under LGPL
- Common for libraries where broader adoption is desired

### Mozilla Public License (MPL) 2.0
- File-level copyleft: modifications to MPL-licensed files must stay under MPL
- New files you add can use a different license
- Good balance between permissive and copyleft

## AGPL Considerations

The **GNU Affero General Public License (AGPL)** deserves special attention for Nava's work:

- Extends GPL's copyleft to network use — if you modify AGPL software and provide it as a network service, you must share your source code
- This is particularly relevant for web applications and government SaaS platforms
- Using AGPL dependencies in Nava projects requires careful review of how the dependency is integrated
- **Consult your engineering lead before adopting AGPL-licensed dependencies**

## License Compatibility

Not all licenses can be combined in a single project. Key compatibility considerations:

| Dependency License | Compatible with Apache 2.0 (Nava default)? |
|---|---|
| MIT | Yes |
| BSD (2/3-Clause) | Yes |
| Apache 2.0 | Yes |
| MPL 2.0 | Yes (file-level separation) |
| LGPLv2.1+ | Yes (if dynamically linked) |
| GPLv2 only | No |
| GPLv3 | Yes (but project becomes GPLv3) |
| AGPL | Requires review |

## When to Seek Guidance

Reach out to your engineering lead or the Nava open source team when:

- You encounter a license not listed here
- A dependency uses a dual-license model
- You're unsure whether your use constitutes a "derivative work"
- You want to use an AGPL-licensed dependency
- A project uses a custom or modified license

---

**Back to**: [Using Open Source](index.md) | [Nava Open Source Guide](../../README.md)
