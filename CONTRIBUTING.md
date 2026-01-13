# Contributing to ZeroPay

Thank you for your interest in contributing to **ZeroPay**.  
ZeroPay is a security-first, open-source payment execution engine, and contributions are expected to meet a high standard of correctness, safety, and clarity.

This document outlines how to contribute responsibly.

---

## Core Philosophy

ZeroPay is built with the following priorities:

1. **Security over convenience**
2. **Correctness over speed**
3. **Clarity over cleverness**
4. **Fail-secure behavior over feature richness**

All contributions must align with these principles.

---

## Types of Contributions

We welcome the following kinds of contributions:

- Bug fixes
- Security improvements
- Documentation improvements
- Test coverage
- Performance optimizations
- Refactoring for clarity or safety
- New payment provider implementations (behind abstractions)

Before starting large changes, please open an issue to discuss your approach.

---

## What We Do NOT Accept

To protect the integrity of the project, the following will not be accepted:

- Features that weaken isolation or security guarantees
- Direct handling or storage of raw payment credentials
- Bypassing validation, policy checks, or state machines
- Adding unnecessary dependencies
- Experimental cryptography or custom crypto implementations
- Changes without tests where tests are feasible
- Large changes without prior discussion

---

## Getting Started

1. Fork the repository
2. Create a feature branch from `main`
3. Make your changes
4. Ensure tests pass
5. Open a pull request

Keep pull requests focused and minimal.

---

## Code Standards

### Language
- Rust (stable channel)

### General Guidelines
- Prefer explicit over implicit behavior
- Avoid `unsafe` unless absolutely necessary
- Document all security-relevant logic
- Handle errors explicitly (no silent failures)
- No panics in request-handling paths
- Keep APIs minimal and well-defined

---

## Security-Sensitive Code

If your contribution touches any of the following areas:

- Authentication or authorization
- Cryptography
- Payment state machines
- Intrusion detection
- Network boundaries
- Secrets handling

You **must**:
- Clearly document your changes
- Explain the security impact
- Avoid breaking existing guarantees

Security-sensitive pull requests may take longer to review.

---

## Testing Requirements

All functional changes should include appropriate tests where possible.

Expected testing includes:
- Unit tests for logic
- State transition validation
- Error and edge-case handling

Security-related changes may require additional review or testing.

---

## Commit Messages

Use clear, descriptive commit messages:

