# UI_SPECIFICATION.md

# IncomeProof — User Interface Specification

**Version:** 1.0
**Status:** Approved

---

# 1. Purpose

This document defines the complete frontend experience for the IncomeProof MVP.

It specifies:

* Information Architecture
* Navigation
* User Flows
* Screens
* Components
* Layouts
* Responsive Behavior
* UI States

This document intentionally excludes backend implementation.

---

# 2. Design Principles

The interface should communicate:

* Trust
* Simplicity
* Professionalism
* Transparency

The design language should resemble modern fintech products rather than blockchain applications.

Users should not need blockchain knowledge.

---

# 3. Design System

Style:

* Modern
* Minimal
* Enterprise-grade
* Clean spacing
* Accessible typography

Framework:

* Tailwind CSS
* shadcn/ui
* Lucide Icons

---

# 4. Navigation Structure

```text
IncomeProof

├── Dashboard
├── Issue Credential
├── Credentials
├── Verification
└── Settings (Placeholder)
```

The MVP uses a simple left sidebar on desktop and a bottom navigation drawer on mobile.

---

# 5. Primary User Journey

### Issuer

Dashboard

↓

Issue Credential

↓

Review Information

↓

Credential Issued

↓

View Credential

↓

Copy Verification Link

---

### Worker

Open Credential

↓

View Credential Details

↓

Share Verification Link

---

### Verifier

Open Verification Link

↓

Verification Page

↓

Verified Status

---

# 6. Screens

## 6.1 Dashboard

Purpose:

Provide an overview of issued credentials.

Cards:

* Total Credentials
* Verified Credentials
* Pending Blockchain Anchors
* Recent Activity

Table:

Recent Credentials

Columns:

* Worker
* Organization
* Status
* Issue Date
* Actions

Actions:

* View
* Share

---

## 6.2 Issue Credential

Large multi-section form.

Sections:

### Worker Information

* Full Name
* Worker ID

---

### Employment Information

* Organization
* Position
* Employment Type

---

### Income Information

* Income Amount
* Currency
* Payment Frequency
* Payment Period

---

### Credential Information

* Issue Date
* Notes (Optional)

Bottom Actions:

* Cancel
* Review Credential

---

## 6.3 Review Credential

Display the entered information in read-only format.

Show:

* Worker Information
* Employment Information
* Income Summary
* Credential Details

Actions:

* Back
* Issue Credential

---

## 6.4 Credential Success

Display:

Success illustration

Message:

> Credential Successfully Issued

Information:

* Credential ID
* Issue Date
* Blockchain Status
* Verification Link

Buttons:

* View Credential
* Copy Verification Link
* Issue Another Credential

---

## 6.5 Credential Details

Display:

Credential summary.

Sections:

Worker

Employment

Income

Blockchain Status

Verification Status

Actions:

* Copy Link
* Download Certificate (Placeholder)
* View Verification

---

## 6.6 Verification Page

Public page.

Header:

Credential Verification

Verification Badge

Possible States:

* Verified
* Pending Blockchain Confirmation
* Invalid Credential
* Revoked (Future)

Display:

Issuer

Issue Date

Credential ID

Verification Timestamp

Blockchain Transaction Reference

---

# 7. Reusable Components

Cards

Metric Cards

Data Table

Page Header

Breadcrumbs

Status Badge

Timeline

Loading Spinner

Skeleton Loader

Toast Notifications

Confirmation Dialog

Copy Button

Search Field

Pagination

Modal

Drawer

---

# 8. Credential Status Badges

Draft

Pending

Anchoring

Verified

Failed

Archived

Each badge must have consistent styling.

---

# 9. Trust Timeline

Every credential displays:

```
Credential Created

↓

Hash Generated

↓

Proof Anchored

↓

Credential Verified
```

This timeline helps users understand the credential lifecycle without exposing blockchain complexity.

---

# 10. Empty States

Dashboard

"No credentials have been issued yet."

Credentials

"No credentials found."

Verification

"Enter a verification link."

---

# 11. Loading States

Use skeleton loaders.

Never display blank pages.

Buttons should indicate loading during actions.

---

# 12. Error States

Friendly messaging only.

Examples:

Unable to issue credential.

Unable to load credential.

Verification failed.

Blockchain confirmation pending.

Never expose stack traces or internal errors.

---

# 13. Forms

All forms should include:

Real-time validation

Required field indicators

Helpful validation messages

Keyboard accessibility

Logical tab order

Responsive layout

---

# 14. Responsive Behavior

Desktop:

Sidebar navigation

Two-column layouts where appropriate

Tables

Mobile:

Bottom navigation

Single-column forms

Responsive cards

Collapsible sections

Touch-friendly buttons

---

# 15. Accessibility

Follow WCAG principles.

Requirements:

Keyboard navigation

Screen reader compatibility

Visible focus states

Sufficient color contrast

Accessible labels

---

# 16. Icons

Use Lucide Icons consistently.

Examples:

Home

User

Building

Wallet

Shield Check

Clipboard

Link

Search

Settings

Clock

---

# 17. Color Philosophy

Primary:

Professional blue

Secondary:

Neutral gray

Success:

Green

Warning:

Amber

Error:

Red

Avoid excessive gradients and blockchain-themed styling.

The interface should communicate trust and professionalism.

---

# 18. Mock Data

Lovable should use realistic mock data.

Example:

Worker:

Maria Santos

Employer:

ABC Manufacturing Inc.

Income:

₱35,000 Monthly

Status:

Verified

Blockchain:

Anchored Successfully

Use at least 10 realistic sample credentials to populate the dashboard.

---

# 19. What NOT to Build

Do not implement:

* Authentication
* Database access
* REST APIs
* Prisma
* Stellar integration
* Wallet connection
* Smart contracts
* Business logic

Use mock services only.

---

# 20. Deliverables

Lovable should generate:

* Complete application shell
* Responsive layouts
* Reusable components
* Mock data
* Mock services
* Professional UX
* Production-ready frontend structure

The generated frontend should be ready for backend integration without significant restructuring.
