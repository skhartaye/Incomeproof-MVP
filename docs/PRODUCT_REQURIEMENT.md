# PRODUCT_REQUIREMENTS_DOCUMENT.md

# IncomeProof — Product Requirements Document (PRD)

**Version:** 1.0
**Status:** Approved for MVP Development

---

# 1. Executive Summary

IncomeProof is a trust infrastructure platform that enables trusted organizations to issue verifiable income credentials. These credentials are owned by workers and can be securely shared with third parties, who can independently verify their authenticity through cryptographic proofs anchored on the Stellar blockchain.

The MVP focuses on solving the problem of manual and repetitive income verification while maintaining privacy and data integrity.

---

# 2. Problem Statement

Income verification is currently:

* Slow
* Manual
* Expensive
* Easy to falsify
* Difficult to reuse

Workers repeatedly submit payslips, employment certificates, or screenshots whenever they apply for financial services, rental housing, scholarships, or employment. Organizations must repeatedly respond to verification requests, creating unnecessary operational overhead.

---

# 3. Proposed Solution

IncomeProof provides a platform where trusted organizations issue cryptographically verifiable income credentials.

Each credential:

* Represents verified income information.
* Is cryptographically hashed.
* Has its proof anchored on the Stellar blockchain.
* Can be shared using a verification link.
* Can be independently verified without contacting the issuing organization.

No personally identifiable information is stored on-chain.

---

# 4. Product Goals

## Primary Goals

* Simplify income verification.
* Reduce fraud through cryptographic integrity.
* Eliminate repeated verification requests.
* Provide reusable credentials.
* Demonstrate practical blockchain adoption.

---

## Success Metrics (MVP)

* An issuer can issue a credential in under 2 minutes.
* A worker can access and share a credential in under 30 seconds.
* A verifier can confirm authenticity in under 60 seconds.
* Blockchain anchoring completes successfully.
* Verification works without requiring blockchain knowledge.

---

# 5. Target Users

## Primary Users

Trusted organizations responsible for issuing income credentials.

Examples:

* Employers
* Payroll providers
* Universities
* Government agencies
* Scholarship providers

---

## Secondary Users

Workers who receive, own, and share issued credentials.

---

## Tertiary Users

Organizations verifying income credentials.

Examples:

* Banks
* Lending platforms
* Landlords
* Insurance providers
* Employers

---

# 6. User Personas

## Issuer

**Goal**

Issue accurate, trustworthy income credentials quickly.

**Needs**

* Simple workflow
* Reliable issuance
* Secure processing

---

## Worker

**Goal**

Receive and reuse verified income credentials.

**Needs**

* Easy access
* Shareable links
* Confidence in authenticity

---

## Verifier

**Goal**

Determine whether a credential is authentic.

**Needs**

* Fast verification
* Clear status
* Trusted issuer information

---

# 7. Functional Requirements

## FR-001 Credential Issuance

The platform shall allow an authorized issuer to create a verified income credential.

Required information:

* Worker name
* Worker identifier
* Organization
* Employment type
* Income amount
* Currency
* Payment frequency
* Payment period
* Issue date

---

## FR-002 Credential Review

Before issuance, the issuer shall review all entered information.

---

## FR-003 Credential Generation

Upon confirmation, the platform shall:

* Create a VerifiedIncomeRecord.
* Generate a canonical representation.
* Compute a cryptographic hash.
* Queue blockchain anchoring.
* Generate a verification token.

---

## FR-004 Credential View

Workers shall be able to:

* View issued credentials.
* View blockchain status.
* View verification status.
* Share credentials.

---

## FR-005 Public Verification

Anyone with a verification link shall be able to:

* Confirm credential authenticity.
* View issuing organization.
* View credential summary.
* View blockchain verification status.

No authentication is required for public verification.

---

## FR-006 Blockchain Integrity

The platform shall anchor only cryptographic proof data to the Stellar blockchain.

No PII shall be written on-chain.

---

## FR-007 Trust Timeline

Each credential shall display a visual trust timeline showing:

1. Credential issued.
2. Proof generated.
3. Proof anchored.
4. Credential ready for sharing.

---

# 8. Non-Functional Requirements

## Performance

* Responsive user interface.
* Efficient verification workflow.
* Fast page loading.

---

## Security

* No PII stored on-chain.
* Secure credential generation.
* Strong input validation.
* Secure server-side processing.

---

## Scalability

The architecture shall support future integration with:

* Payroll systems
* HR platforms
* Wallet providers
* Financial institutions
* Government agencies

---

## Reliability

Credential integrity shall remain verifiable even if the issuing organization is unavailable.

---

# 9. Business Rules

* Trust originates from the issuer.
* Workers own credentials after issuance.
* Verifiers never modify credentials.
* Blockchain preserves integrity only.
* VerifiedIncomeRecord is the Single Source of Truth.

---

# 10. Out of Scope (MVP)

The MVP does **not** include:

* Payroll processing
* Salary disbursement
* Stablecoin payments
* Lending
* Identity verification
* Wallet management
* KYC
* Multi-organization administration
* Credential revocation
* AI risk analysis

These are future roadmap items.

---

# 11. User Journeys

## Journey 1 — Issue Credential

Issuer enters information → Reviews details → Issues credential → Credential is generated → Blockchain proof is anchored → Credential becomes shareable.

---

## Journey 2 — View Credential

Worker opens credential → Reviews details → Shares verification link.

---

## Journey 3 — Verify Credential

Verifier opens shared link → Platform validates proof → Verification result is displayed.

---

# 12. Acceptance Criteria

The MVP is considered complete when:

* Issuers can create credentials.
* Workers can access issued credentials.
* Verification links function correctly.
* Blockchain proof is successfully anchored.
* Public verification confirms authenticity.
* No PII is stored on-chain.
* The UI supports desktop and mobile devices.
* The application follows the approved architecture.

---

# 13. Risks

Potential risks include:

* Incorrect issuer data entry.
* Blockchain service interruptions.
* User misunderstanding of blockchain concepts.
* Credential misuse outside intended workflows.

Mitigations include:

* Review screens before issuance.
* Asynchronous blockchain processing.
* Clear verification messaging.
* Strong input validation.

---

# 14. Future Roadmap

Future versions may introduce:

* Stablecoin salary disbursement.
* Additional credential types.
* Wallet integration.
* Credential revocation.
* Organization management.
* Public APIs.
* Open protocol support.
* Financial service integrations.

These enhancements must preserve the existing trust model and Single Source of Truth.

---

# 15. Definition of Done

The MVP is complete when:

* The three core user journeys are fully functional.
* All functional requirements are satisfied.
* Blockchain proof anchoring operates successfully.
* Verification is independent and reliable.
* The architecture adheres to the Engineering Constitution.
* The platform is ready for demonstration and further iteration.

---

# Approval

This PRD defines the functional scope of IncomeProof MVP and serves as the primary product reference for design, development, and testing.

Implementation details are documented separately in the engineering specifications.
