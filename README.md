# IncomeProof

> **Building verifiable financial trust through blockchain-backed income credentials.**

---

# Overview

IncomeProof is a trust infrastructure platform that enables trusted organizations to issue **verifiable income credentials** that workers own and can securely share with third parties.

Instead of relying on screenshots, manually generated certificates, or unverifiable employment letters, IncomeProof creates cryptographically verifiable income records whose integrity is anchored on the Stellar blockchain.

The platform is designed around one simple principle:

> **The issuer creates the proof. The worker owns the credential. Anyone can verify its authenticity.**

IncomeProof does **not** replace payroll systems.

Instead, it acts as a trust layer that sits between organizations, workers, and verifiers.

---

# Problem Statement

Income verification remains slow, manual, and easy to falsify.

Workers frequently need to prove their income when applying for:

* Loans
* Rental housing
* Scholarships
* Financial services
* Employment opportunities

Current methods rely on:

* Payslips
* Employment certificates
* Screenshots
* PDFs
* Emails

These documents can be altered, are difficult to verify, and require organizations to repeatedly respond to verification requests.

---

# Solution

IncomeProof enables trusted organizations to issue cryptographically verifiable income credentials.

Each issued credential:

* Represents a verified income record.
* Produces a deterministic cryptographic proof.
* Anchors that proof on the Stellar blockchain.
* Generates a shareable verification link.
* Allows anyone with permission to independently verify authenticity.

No personally identifiable information (PII) is written to the blockchain.

Only a cryptographic proof of integrity is anchored.

---

# Vision

Create an open trust infrastructure where verified income credentials become reusable financial assets.

A worker should receive one trusted credential and reuse it across multiple financial services without repeatedly requesting documentation from employers.

---

# Target Users

## Primary

Trusted issuing organizations such as:

* Employers
* Payroll providers
* Universities
* Scholarship offices
* Government programs
* Freelancer platforms

## Secondary

Workers who receive and share verified credentials.

## Tertiary

Organizations that verify income credentials, including:

* Banks
* Lending platforms
* Property managers
* Insurance providers
* Financial institutions

---

# Core Principles

## Trust by Issuance

Trust begins with the issuing organization.

IncomeProof does not determine whether income is true.

It preserves the integrity of information issued by trusted organizations.

---

## Privacy by Design

Sensitive personal information never resides on-chain.

Blockchain stores only cryptographic proof.

---

## Single Source of Truth

The entire platform is built around one business entity:

**VerifiedIncomeRecord**

Every certificate, QR code, verification page, and blockchain proof is derived from this record.

No duplicate business data exists.

---

## Blockchain as Infrastructure

Blockchain is not the product.

Blockchain is infrastructure used to preserve integrity.

Users interact with trusted credentials, not blockchain transactions.

---

# MVP Features

## Issuer Portal

* Create verified income credentials
* Review credential information
* Issue credential
* Generate verification link

---

## Worker Credential

* View credential
* Share credential
* View blockchain verification status

---

## Public Verification

* Verify authenticity
* View issuing organization
* View verification status
* Confirm blockchain proof

---

# Technology Stack

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

---

# Repository Structure

```text
docs/
    product/
    architecture/
    engineering/
    demo/

prisma/

src/

public/
```

---

# Development Philosophy

IncomeProof follows Domain-Driven Design principles.

Business logic is separated from infrastructure.

Every architectural decision must preserve:

* Single Source of Truth
* Trust-first design
* Privacy by design
* Minimal complexity
* Extensibility

The project intentionally avoids premature enterprise architecture while remaining production-ready.

---

# Current Status

Planning and architecture are complete.

The project is currently entering implementation.

Development will proceed in milestones:

1. Project Foundation
2. Domain Layer
3. Blockchain Integration
4. REST API
5. User Interface
6. Demo Readiness

---

# Hackathon Alignment

IncomeProof is being developed as a submission for the **APAC Stellar Hackathon**.

The MVP demonstrates how Stellar can provide real-world utility by enabling trusted organizations to issue reusable, blockchain-backed financial credentials.

The long-term vision extends beyond the hackathon into a scalable trust infrastructure for financial verification.

---

# License

License selection will be finalized before the public repository launch.

---

# Contributing

Contribution guidelines will be published as the project enters collaborative development.

---

# Acknowledgements

IncomeProof is designed using a trust-first architecture focused on solving real-world income verification challenges through modern software engineering principles and the Stellar ecosystem.
