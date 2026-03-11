# Copyright Guidance

Understanding copyright is essential for publishing and using open source software. This guide covers copyright as it applies to Nava's work, particularly in the government technology context.

## Copyright at Nava

### Who Holds Copyright
- Code written by Nava employees as part of their work is generally owned by Nava PBC
- Copyright ownership in government contract work depends on the specific contract terms
- Federal government employees' work is generally in the public domain (not copyrightable)
- Nava, as a contractor, retains copyright on code it writes unless the contract specifies otherwise

### Work-for-Hire in Government Context
Government contracts often use FAR clauses that define data rights:

- **Unlimited rights**: The government can use, modify, and distribute the software without restriction
- **Government Purpose Rights (GPR)**: The government can use it for government purposes; broader distribution is restricted for a period
- **Limited/Restricted rights**: More constrained use by the government

Even when the government has unlimited rights, Nava may retain copyright. Consult with Nava's contracts team for specifics on your project.

## Copyright Notices

### Format
Include copyright notices in the `LICENSE` file and optionally in source file headers:

```
Copyright [year] Nava PBC
```

Use the year of first publication. You can use a range (e.g., `2023-2025`) for ongoing work.

### Source File Headers
For Apache 2.0 licensed projects, add headers to source files:

```
// Copyright [year] Nava PBC
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//     http://www.apache.org/licenses/LICENSE-2.0
```

Not all files need headers. Skip headers for:
- Configuration files (JSON, YAML, TOML)
- Data files
- Very short files (under ~10 lines of code)
- Files where headers would break functionality

## Third-Party Copyright

When using third-party open source code:

- **Preserve copyright notices**: Never remove or alter existing copyright notices
- **Attribution**: Follow the license's attribution requirements (most require keeping the copyright notice)
- **NOTICE file**: If your project includes Apache 2.0 licensed code from others, maintain a `NOTICE` file listing their attributions

---

**Back to**: [Resources](index.md) | [Nava Open Source Guide](../../README.md)
