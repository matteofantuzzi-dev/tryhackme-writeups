# Case Study: CVE-2024-3094 (XZ Utils Backdoor)

## Overview
CVE-2024-3094 is a critical supply chain attack involving a malicious backdoor
introduced into XZ Utils, a widely used compression utility and library on Linux systems.

## Affected Component
- XZ Utils (`xz`)
- `liblzma` library
- Versions 5.6.0 and 5.6.1

## Attack Type
- Supply chain attack
- Backdoor insertion
- Trust abuse in open-source software

## Impact
- Potential remote unauthorized access
- Interference with OpenSSH authentication
- High risk for Linux-based systems

## Discovery
The backdoor was discovered during performance analysis and debugging,
before widespread deployment in stable Linux distributions.

## Security Lessons Learned
- Even trusted open-source projects can be targeted
- Code reviews and reproducible builds are critical
- Monitoring dependencies is essential for system security

## Defensive Takeaways
- Avoid running bleeding-edge packages in production
- Monitor CVEs for core system libraries
- Use integrity checks and minimal privilege principles
