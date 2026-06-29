# SYSTEM_ARCHITECTURE.md

# IncomeProof — System Architecture

**Version:** 1.0
**Status:** Approved

---

# 1. Purpose

This document defines the overall technical architecture of IncomeProof.

It describes how the application's components interact, where responsibilities belong, and the architectural principles that guide implementation.

This document is the authoritative reference for system organization and must remain consistent with the Engineering Constitution and Product Requirements Document.

---

# 2. Architecture Goals

The system is designed to achieve the following objectives:

* Preserve trust through verifiable credentials.
* Protect user privacy.
* Keep business logic independent of infrastructure.
* Enable future protocol expansion.
* Support maintainability through modular design.
* Minimize coupling between layers.

---

# 3. Architectural Principles

IncomeProof follows these principles:

* Domain-Driven Design (DDD)
* Single Source of Truth (SSOT)
* Separation of Concerns
* Clean Architecture
* API-first design
* Infrastructure independence
* Privacy by design
* Blockchain as supporting infrastructure

---

# 4. High-Level Architecture

```text
                           ┌────────────────────┐
                           │       Issuer       │
                           └─────────┬──────────┘
                                     │
                           ┌─────────▼──────────┐
                           │    Next.js UI      │
                           │ (Frontend Shell)   │
                           └─────────┬──────────┘
                                     │
                           ┌─────────▼──────────┐
                           │     REST API       │
                           │ (Route Handlers)   │
                           └─────────┬──────────┘
                                     │
                    ┌────────────────┴────────────────┐
                    │                                 │
          ┌─────────▼─────────┐             ┌────────▼────────┐
          │ Domain Services   │             │ Validation      │
          │ Business Logic    │             │ (Zod Schemas)   │
          └─────────┬─────────┘             └─────────────────┘
                    │
          ┌─────────▼─────────┐
          │ Repository Layer  │
          └─────────┬─────────┘
                    │
          ┌─────────▼─────────┐
          │ Prisma ORM        │
          └─────────┬─────────┘
                    │
          ┌─────────▼─────────┐
          │ PostgreSQL        │
          └─────────┬─────────┘
                    │
      ┌─────────────┴─────────────┐
      │                           │
┌─────▼─────────┐         ┌────────▼─────────┐
│ Hash Service  │         │ Stellar Adapter  │
└───────────────┘         └──────────────────┘
```

---

# 5. System Layers

## Presentation Layer

Responsible for:

* User interface
* Forms
* Navigation
* Responsive layouts
* User interactions

Technologies:

* Next.js
* React
* Tailwind CSS
* shadcn/ui

This layer must never contain business logic.

---

## API Layer

Responsible for:

* HTTP request handling
* Authentication (future)
* Validation
* Error handling
* Calling domain services

The API layer should remain thin.

Business decisions belong in the domain layer.

---

## Domain Layer

The domain layer contains the application's core business logic.

Responsibilities include:

* Credential issuance
* Verification rules
* Canonical record generation
* Hash generation
* Credential lifecycle management

This layer must not depend on UI or database implementation details.

---

## Repository Layer

Responsible for:

* Reading data
* Writing data
* Query abstraction

Repositories isolate domain services from the persistence layer.

---

## Infrastructure Layer

Responsible for:

* PostgreSQL
* Prisma ORM
* Stellar SDK
* Cryptographic services
* External integrations

Infrastructure should be replaceable without changing business logic.

---

# 6. Single Source of Truth (SSOT)

The entire system is centered around one domain entity:

**VerifiedIncomeRecord**

It is the only entity that owns business data.

Everything else is derived.

Derived artifacts include:

* Certificates
* QR Codes
* Verification Pages
* Blockchain Anchors
* Verification Tokens

Derived artifacts must never become independent data sources.

---

# 7. Data Flow

## Credential Issuance

```
Issuer
   │
   ▼
Credential Form
   │
   ▼
Validation
   │
   ▼
VerifiedIncomeRecord Created
   │
   ▼
Canonical Representation
   │
   ▼
SHA-256 Hash
   │
   ▼
Store Record
   │
   ▼
Anchor Hash on Stellar
   │
   ▼
Credential Ready
```

---

## Credential Verification

```
Verifier
    │
    ▼
Verification Link
    │
    ▼
Retrieve VerifiedIncomeRecord
    │
    ▼
Recompute Hash
    │
    ▼
Compare Blockchain Proof
    │
    ▼
Verification Result
```

---

# 8. Blockchain Responsibilities

The Stellar blockchain is used only to preserve integrity.

Blockchain stores:

* Hash
* Timestamp
* Transaction reference

Blockchain never stores:

* Worker names
* Income values
* Employer information
* Addresses
* Email addresses
* Government identifiers
* Personally identifiable information (PII)

---

# 9. Security Model

The system follows these principles:

* Validate all inputs.
* Keep sensitive data server-side.
* Use HTTPS in production.
* Never expose secrets to the client.
* Minimize stored sensitive information.
* Protect cryptographic integrity.

---

# 10. Error Handling

Errors are categorized as:

### Validation Errors

Invalid user input.

### Business Errors

Violation of business rules.

### Infrastructure Errors

Database or blockchain failures.

### External Errors

Failures from third-party services.

Each category should return clear, user-friendly messages without exposing internal implementation details.

---

# 11. Scalability Strategy

The architecture supports future expansion through modular services.

Potential future modules include:

* Payroll integrations
* Wallet integrations
* Stablecoin salary disbursement
* Credential revocation
* Identity providers
* Public APIs
* Organization management

These additions should extend the architecture without modifying the existing domain model.

---

# 12. Technology Stack

## Frontend

* Next.js 15
* React
* TypeScript
* Tailwind CSS
* shadcn/ui

## Backend

* Next.js Route Handlers
* Prisma ORM
* PostgreSQL
* Zod

## Blockchain

* Stellar SDK
* Stellar Testnet (MVP)
* Stellar Mainnet (Production)

---

# 13. Design Constraints

The implementation must adhere to the following constraints:

* Business logic belongs only in the domain layer.
* UI must remain presentation-only.
* APIs should orchestrate, not decide.
* Database schema must reflect the domain model.
* Blockchain integration must remain optional from the perspective of business logic.
* Future integrations must preserve backward compatibility.

---

# 14. Definition of Success

The architecture is successful when:

* Components have clear responsibilities.
* Business logic is centralized.
* Infrastructure can evolve independently.
* Credentials remain verifiable.
* Privacy is preserved.
* Future integrations require minimal architectural changes.

---

# 15. Final Architecture Principle

Whenever implementation decisions conflict, prioritize the following order:

1. Preserve the Single Source of Truth.
2. Protect trust.
3. Protect privacy.
4. Maintain separation of concerns.
5. Prefer simplicity over complexity.
6. Build for extension, not modification.
