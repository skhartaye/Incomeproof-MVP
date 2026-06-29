# MASTER_CONTEXT.md

# IncomeProof — Master Context

Version: 1.0

Status: Approved

Purpose: Single source of context for all AI development tools and engineering contributors.

---

# Project Overview

IncomeProof is a trust infrastructure platform that enables trusted organizations to issue cryptographically verifiable income credentials.

The platform allows workers to own reusable income credentials that can be independently verified by third parties without requiring repeated manual verification from the issuing organization.

IncomeProof does not replace payroll, HR, or financial systems.

Instead, it provides a reusable trust layer that connects issuers, credential holders, and verifiers.

---

# Mission

Reduce friction in financial verification by enabling trusted organizations to issue reusable, privacy-preserving income credentials whose integrity is protected through blockchain technology.

---

# Vision

Create an open trust protocol where verified financial credentials become portable digital assets that workers can securely reuse across financial services, employment platforms, housing applications, and other trust-dependent interactions.

IncomeProof aims to become the trust layer—not the payroll system.

---

# Core Product Philosophy

IncomeProof exists to solve one problem:

> **How can a worker prove verified income without repeatedly requesting documents from the issuing organization?**

The platform does not judge whether income is correct.

Trust begins with the issuer.

IncomeProof preserves that trust through cryptographic integrity and independent verification.

---

# Stakeholders

## Issuers

Trusted organizations that create verified income credentials.

Examples:

* Employers
* Payroll providers
* Universities
* Scholarship offices
* Government agencies
* Freelancer marketplaces

---

## Credential Holders

Individuals who receive issued credentials and control when and with whom they share them.

---

## Verifiers

Organizations that verify credential authenticity.

Examples:

* Banks
* Lending platforms
* Landlords
* Insurance companies
* Financial institutions
* Employers

---

# Product Scope (MVP)

The MVP supports three user journeys.

## 1. Credential Issuance

An issuer creates a verified income credential.

The platform:

* validates the data,
* creates a canonical representation,
* generates a cryptographic hash,
* anchors the proof on Stellar,
* stores blockchain metadata,
* issues a shareable credential.

---

## 2. Credential Ownership

The worker views and manages issued credentials.

The worker can:

* view details,
* share a verification link,
* download a certificate (optional),
* monitor verification status.

---

## 3. Public Verification

A verifier opens the shared link.

The platform confirms:

* credential exists,
* credential has not been modified,
* blockchain proof matches,
* credential status is valid,
* issuer identity.

No blockchain knowledge is required by the verifier.

---

# Out of Scope (MVP)

The following are intentionally excluded:

* Payroll processing
* Salary payments
* Stablecoin payroll
* Lending
* Identity verification
* KYC
* Wallet management
* Multi-tenant enterprise administration
* Advanced analytics
* AI risk scoring

These may become future integrations but are not part of the MVP.

---

# Single Source of Truth (SSOT)

The entire platform is centered around one domain entity:

**VerifiedIncomeRecord**

Every derived artifact originates from this entity.

Derived artifacts include:

* Certificates
* QR codes
* Verification pages
* Blockchain proofs
* Share links
* Verification responses

No derived artifact owns business data.

Only `VerifiedIncomeRecord` owns the authoritative data.

---

# Trust Model

Trust flows through three stages:

1. A trusted issuer creates the record.
2. IncomeProof protects the integrity of the record.
3. Any verifier independently confirms authenticity.

IncomeProof does not establish trust—it preserves it.

---

# Blockchain Philosophy

Blockchain is infrastructure.

Blockchain is not the product.

Only cryptographic proofs are written to the Stellar blockchain.

The following must never be stored on-chain:

* Names
* Salaries
* Employer details
* Addresses
* Email addresses
* Phone numbers
* Government IDs
* Personally identifiable information (PII)

---

# Architecture Principles

The platform follows Domain-Driven Design.

## Core principles

* Business logic lives in domain services.
* UI never owns business rules.
* APIs remain thin.
* Infrastructure is replaceable.
* Services are composable.
* Privacy takes precedence over convenience.
* Simplicity is preferred over premature optimization.

---

# Technology Stack

## Frontend

* Next.js 15
* React
* TypeScript
* Tailwind CSS
* shadcn/ui
* React Hook Form
* TanStack Query

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

# High-Level Architecture

```
Issuer
    │
    ▼
Frontend (Next.js)
    │
    ▼
REST API
    │
    ▼
Domain Services
    │
    ▼
Prisma
    │
    ▼
PostgreSQL
    │
    ▼
Hash Generator
    │
    ▼
Stellar Blockchain
```

The blockchain stores only proof metadata.

All business data remains within the application database.

---

# Engineering Rules

Every contributor and AI coding assistant must follow these rules:

1. `VerifiedIncomeRecord` is the SSOT.
2. Never introduce new business entities without approval.
3. Never store PII on-chain.
4. Keep APIs thin.
5. Keep business logic in the domain layer.
6. Do not duplicate business data.
7. Use composition over duplication.
8. Prefer readability over cleverness.
9. Keep the MVP focused.
10. Every implementation must support future protocol evolution.

---

# AI Development Rules

AI coding assistants must:

* follow this document before any prompt,
* preserve the approved architecture,
* avoid inventing workflows,
* avoid adding speculative enterprise features,
* avoid changing domain terminology,
* implement only the requested milestone.

---

# Folder Philosophy

The project uses a domain-oriented structure rather than a technology-oriented structure.

Each feature owns its UI, services, validation, and business logic while respecting shared architectural boundaries.

---

# Future Evolution

The MVP establishes the foundation for a broader trust protocol.

Potential future integrations include:

* Payroll systems
* Freelancer marketplaces
* Universities
* Government agencies
* Lending platforms
* Wallet providers
* Identity providers

These integrations extend the platform without changing the core trust model.

---

# Definition of Success

IncomeProof succeeds when:

* trusted organizations can issue verifiable income credentials,
* workers can securely reuse them,
* verifiers can independently confirm authenticity,
* no sensitive information is exposed on-chain,
* the platform remains simple, trustworthy, and extensible.

---

# Final Principle

Whenever implementation decisions conflict, prioritize the following in order:

1. Protect trust.
2. Protect privacy.
3. Preserve the Single Source of Truth.
4. Keep the architecture simple.
5. Deliver a usable product before expanding scope.
