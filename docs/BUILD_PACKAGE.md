# BUILD_PACKAGE.md

# IncomeProof — Build Package

**Version:** 1.0
**Status:** Approved

---

# Purpose

This document defines the official engineering standards, technology stack, project structure, development workflow, and implementation constraints for the IncomeProof MVP.

Every contributor and AI coding assistant must follow this document throughout development.

---

# Project Philosophy

IncomeProof is built as a modern, production-ready web application.

The project prioritizes:

* Simplicity
* Maintainability
* Scalability
* Trust
* Privacy
* Developer Experience

The MVP should avoid unnecessary complexity while remaining extensible for future growth.

---

# Technology Stack

## Frontend

* Next.js 15 (App Router)
* React 19
* TypeScript
* Tailwind CSS
* shadcn/ui
* Lucide React
* React Hook Form
* TanStack Query

---

## Backend

* Next.js Route Handlers
* TypeScript
* Prisma ORM
* PostgreSQL
* Zod

---

## Blockchain

* Stellar SDK
* Stellar Testnet (MVP)
* Stellar Mainnet (Future)

---

## Development Tools

* ESLint
* Prettier
* Husky (Future)
* lint-staged (Future)

---

# Project Structure

```text
incomeproof/

├── app/
│   ├── (dashboard)/
│   ├── issue/
│   ├── credentials/
│   ├── verify/
│   ├── api/
│   └── layout.tsx
│
├── components/
│   ├── ui/
│   ├── shared/
│   ├── dashboard/
│   ├── credential/
│   └── verification/
│
├── lib/
│   ├── validation/
│   ├── utils/
│   ├── constants/
│   └── mock/
│
├── services/
│   ├── domain/
│   ├── blockchain/
│   ├── repositories/
│   └── api/
│
├── prisma/
│
├── public/
│
├── docs/
│
└── types/
```

---

# Folder Responsibilities

## app/

Contains routes and page composition.

No business logic.

---

## components/

Reusable UI components.

Components should remain presentation-focused.

---

## services/

Business logic.

Future:

* Credential issuance
* Verification
* Blockchain
* Repository layer

---

## lib/

Utilities.

Validation.

Constants.

Mock data.

Helper functions.

---

## prisma/

Database schema.

Migrations.

Seed files.

---

# Coding Standards

Use:

* TypeScript strict mode
* Functional components
* Composition over inheritance
* Named exports
* Async/await
* Strong typing

Avoid:

* `any`
* Large files
* Deep component nesting
* Duplicate logic

---

# Naming Conventions

Components:

```text
CredentialCard.tsx
```

Hooks:

```text
useCredentials.ts
```

Services:

```text
credential.service.ts
```

Repositories:

```text
credential.repository.ts
```

Types:

```text
credential.types.ts
```

Constants:

```text
credential.constants.ts
```

---

# UI Standards

Every page should include:

* Page title
* Description
* Breadcrumb (where appropriate)
* Consistent spacing
* Loading state
* Empty state
* Error state

Use reusable components whenever possible.

---

# Form Standards

React Hook Form

Zod validation

Accessible labels

Inline validation messages

Logical tab order

Keyboard support

---

# State Management

For MVP:

* React State
* Context (only if necessary)
* TanStack Query for server state

Do not introduce Redux or other global state libraries.

---

# Styling

Tailwind CSS

shadcn/ui

Responsive first

Consistent spacing scale

No inline styles except where unavoidable.

---

# Icons

Use Lucide React.

Maintain consistent sizing.

Do not mix icon libraries.

---

# Performance

Use:

* Server Components where appropriate
* Lazy loading
* Dynamic imports
* Optimized images
* Memoization only when justified

Avoid premature optimization.

---

# Accessibility

WCAG-compliant

Keyboard navigation

Focus states

ARIA labels where appropriate

Color contrast

Semantic HTML

---

# Mock Data

Lovable should implement realistic mock services.

No API calls.

No database.

No blockchain integration.

Provide reusable mock datasets.

---

# Testing Strategy

Initial MVP:

Manual testing.

Component verification.

Responsive testing.

Future:

Unit tests

Integration tests

End-to-end tests

---

# Git Workflow

Recommended branches:

```text
main
develop
feature/*
bugfix/*
```

Commit style:

```text
feat:
fix:
refactor:
docs:
test:
chore:
```

---

# Environment Variables

Future:

```text
DATABASE_URL=

STELLAR_NETWORK=

STELLAR_SECRET_KEY=

NEXT_PUBLIC_APP_URL=
```

Lovable should not require these values.

---

# MVP Boundaries

Lovable should implement only:

* Frontend pages
* Components
* Mock services
* Navigation
* Responsive layouts

Lovable must not implement:

* Authentication
* Database
* Prisma
* REST API
* Blockchain
* Stellar SDK
* Cryptographic hashing

These will be implemented during the backend phase.

---

# Definition of Done

The generated frontend is complete when:

* All screens from the UI Specification exist.
* Navigation works.
* Components are reusable.
* Responsive layouts function correctly.
* Mock data populates the application.
* Code is clean, typed, and maintainable.
* Integration points for backend services are clearly defined.

---

# Final Engineering Principles

Every implementation should satisfy the following:

1. Keep the architecture simple.
2. Preserve the Single Source of Truth.
3. Separate presentation from business logic.
4. Prioritize readability.
5. Prefer reusable components.
6. Build for future integration.
7. Never expose sensitive information.
8. Do not over-engineer the MVP.

---

# Approval

This Build Package is the official engineering guide for the IncomeProof MVP.

It serves as the implementation baseline for AI coding assistants and human contributors.
