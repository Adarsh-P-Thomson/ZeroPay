# ZeroPay

**ZeroPay** is an open-source, security-first payment execution engine built in Rust.  
It is designed to run as an isolated service that processes payments securely in untrusted or partially trusted environments.

ZeroPay separates payment execution from application logic and enforces strict isolation, minimal APIs, and intrusion-aware behavior.

---

## What ZeroPay Is

ZeroPay is a **payment enclave**.

It runs as a hardened, containerized service that:
- Executes payment operations
- Holds payment-related secrets
- Exposes only a small, well-defined API surface
- Treats the host application as untrusted by default

If abnormal or malicious behavior is detected, ZeroPay is designed to **fail secure**.

---

## What ZeroPay Is Not

- ❌ A frontend payment SDK
- ❌ A UI or checkout framework
- ❌ A replacement for payment service providers
- ❌ A general-purpose backend service

ZeroPay focuses only on **secure payment execution and isolation**.

---

## Why ZeroPay Exists

In many systems, payment logic runs inside large application backends that are difficult to fully secure.  
A single vulnerability can expose payment secrets or allow unauthorized transactions.

ZeroPay reduces this risk by moving all sensitive payment execution into an isolated runtime with a zero-trust design.

---

## High-Level Architecture

Client
↓
Application Backend (Untrusted)
↓
ZeroPay (Isolated Payment Enclave)
↓
Payment Service Provider (PSP)


- The backend never accesses payment secrets
- All payment logic lives inside ZeroPay
- Communication is restricted to a strict API contract

---

## Core Principles

- **Zero-Trust Architecture**  
  The surrounding application is assumed to be untrusted.

- **Hard Isolation**  
  ZeroPay runs with minimal privileges, a read-only filesystem, and a reduced attack surface.

- **Intrusion-Aware Behavior**  
  Abnormal requests, invalid state transitions, or policy violations trigger protective actions.

- **Provider Neutrality**  
  Payment providers are integrated through an abstraction layer.

- **Open and Auditable**  
  The system is designed for transparency and security review.

---

## Key Features

- Memory-safe Rust core
- Minimal HTTP/gRPC API surface
- Strict request validation and schema enforcement
- Payment state machine with explicit transitions
- Provider abstraction (e.g., Stripe, Razorpay, Adyen)
- Runtime self-protection and sealing behavior
- Container-first deployment model

---

## Deployment Model

ZeroPay is intended to run as a standalone service, typically deployed as:

- A rootless Docker container
- With a read-only filesystem
- With no shell access
- With outbound network access limited to approved PSP endpoints

---

## Project Status

🚧 **Early-stage development**

The API, internal architecture, and security mechanisms are still evolving.  
Breaking changes may occur before a stable release.

---

## Security

Security discussions, audits, and responsible disclosure are welcome.  
Detailed threat models and security guarantees will be documented as the project matures.

---

## License

MIT License

---

## Vision

> Payment execution should be isolated, minimal, and defensively designed.

ZeroPay aims to become a reliable open-source foundation for secure payment execution in zero-trust environments.


