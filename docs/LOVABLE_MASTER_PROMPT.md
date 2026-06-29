# LOVABLE_MASTER_PROMPT.md

# IncomeProof — AI Build Contract for Lovable

**Version:** 1.0
**Audience:** Lovable AI Coding Assistant

---

# Your Role

You are the frontend engineering team responsible for building the **IncomeProof MVP Frontend Shell**.

You are **not** responsible for designing the product.

You are **not** responsible for changing the architecture.

You are implementing an already-approved product.

Follow every document in the `/docs` folder.

If any document conflicts, follow this priority:

1. MASTER_CONTEXT.md
2. PRODUCT_REQUIREMENTS_DOCUMENT.md
3. SYSTEM_ARCHITECTURE.md
4. UI_SPECIFICATION.md
5. BUILD_PACKAGE.md

Do not invent missing requirements.

---

# About IncomeProof

IncomeProof is a trust infrastructure platform.

Trusted organizations issue verifiable income credentials.

Workers own those credentials.

Third parties verify authenticity.

Blockchain is used only to preserve integrity.

The application should feel like a modern financial SaaS—not a crypto wallet or blockchain explorer.

---

# Your Objective

Generate a complete frontend application shell that is ready for backend integration.

The application should appear production-ready while using mock data and mock services.

Focus on:

* User experience
* Accessibility
* Responsive layouts
* Reusable components
* Clean code
* Clear architecture

---

# Required Technology Stack

Use:

* Next.js 15 (App Router)
* React 19
* TypeScript
* Tailwind CSS
* shadcn/ui
* Lucide React
* React Hook Form
* TanStack Query

Do not substitute frameworks or libraries unless explicitly requested.

---

# Build the Following Pages

## Dashboard

Display:

* KPI cards
* Recent credentials
* Quick actions

---

## Issue Credential

Build a complete multi-step form including:

* Worker Information
* Employment Information
* Income Information
* Credential Review
* Success Page

---

## Credentials

Display issued credentials using realistic mock data.

Include:

* Search
* Filters
* Status badges
* Pagination
* Action menu

---

## Credential Details

Display:

* Worker summary
* Employment summary
* Income summary
* Verification status
* Trust timeline
* Blockchain status (mock)

---

## Public Verification

Display:

* Verification result
* Issuer
* Credential status
* Blockchain confirmation
* Verification timestamp

Include success, pending, and invalid states.

---

# Navigation

Desktop:

* Left sidebar
* Top navigation bar

Mobile:

* Bottom navigation
* Responsive drawer

All pages should be fully responsive.

---

# Required Components

Create reusable components for:

* Buttons
* Cards
* Data tables
* Status badges
* Metric cards
* Breadcrumbs
* Page headers
* Form fields
* Timeline
* Search bar
* Pagination
* Confirmation dialog
* Toast notifications
* Skeleton loaders
* Empty states
* Error states

Do not duplicate component logic.

---

# Design Language

The interface should communicate:

* Trust
* Simplicity
* Professionalism
* Transparency

Avoid blockchain-themed visuals.

Do not use glowing effects, neon colors, token icons, or cryptocurrency dashboards.

Design inspiration should come from:

* Modern fintech platforms
* Banking dashboards
* Enterprise SaaS products

---

# Mock Data

Generate realistic mock data.

Examples include:

Organizations:

* ABC Manufacturing
* StellarTech Solutions
* Nova Logistics

Workers:

* Maria Santos
* John Reyes
* Angela Cruz

Statuses:

* Draft
* Pending
* Anchoring
* Verified
* Failed

Populate the dashboard with realistic examples.

---

# Project Structure

Organize the project using this structure:

```text
app/
components/
lib/
services/
types/
public/
```

Separate reusable UI components from page composition.

---

# Code Quality Requirements

All code must:

* Use strict TypeScript.
* Use functional React components.
* Follow clean naming conventions.
* Avoid duplicate code.
* Prefer composition over inheritance.
* Keep components small and reusable.

---

# Accessibility Requirements

The application must support:

* Keyboard navigation
* Focus indicators
* Screen readers
* Semantic HTML
* Proper labels
* Responsive layouts

Follow WCAG best practices.

---

# Performance Requirements

Generate code that supports:

* Fast initial loading
* Lazy-loaded pages where appropriate
* Optimized rendering
* Minimal unnecessary re-renders

Do not optimize prematurely.

---

# Explicitly Do NOT Build

Do not implement:

* Authentication
* Authorization
* Database access
* Prisma
* PostgreSQL
* REST APIs
* GraphQL
* Blockchain transactions
* Stellar SDK
* Wallet connections
* Cryptographic hashing
* Server-side business logic
* Environment variable configuration

Use mock services only.

---

# Integration Boundaries

Prepare the frontend for future backend integration.

Use clearly named placeholder services such as:

* CredentialService
* VerificationService
* DashboardService

These services should return mock data only.

Avoid coupling UI directly to implementation details.

---

# Deliverables

Generate:

* Complete application shell
* Responsive layouts
* Reusable component library
* Mock services
* Mock data
* Routing
* Clean folder structure
* Professional UX

The project should be ready for backend implementation without significant refactoring.

---

# Definition of Success

The frontend is considered complete when:

* All pages from the UI Specification are implemented.
* Navigation works on desktop and mobile.
* Components are reusable.
* Mock data demonstrates the complete user journey.
* The application looks and behaves like a production-ready financial platform.
* Integration points are prepared for future backend services.

---

# Final Instructions

Do not redesign IncomeProof.

Do not introduce additional workflows.

Do not create extra user roles.

Do not add speculative features.

Do not expand the MVP scope.

Implement only what has been specified.

When uncertain, choose the simplest solution that preserves the approved architecture.

The frontend you generate will become the foundation for backend implementation using Kiro.
