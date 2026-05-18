# Product Build Spec Template

```md
# Product Build Spec: [Project Name]

## 1. Product Summary

### One-sentence Definition

这是一个面向【目标用户】的【产品类型】，帮助他们在【具体场景】中解决【核心痛点】，通过【核心功能】获得【明确结果】。

### Target User

### Core Pain Point

### Why Users Would Pay

### Expected Delivery Model

### Expected Sales Channel

### MVP Success Signal

---

## 2. Assumptions

List assumptions made due to missing information.

---

## 3. Target User and Core Pain Point

| User Segment | Scenario | Pain Point | Payment Motivation |
|---|---|---|---|

---

## 4. Product Shape Decision

### Recommended First-Version Shape

### Why This Shape

### Not Recommended for v0.1

---

## 5. MVP Scope

### Must-have

### Should-have

### Nice-to-have

### Non-goals

---

## 6. User Roles

| Role | Can See | Can Do | Cannot Do | State Changes |
|---|---|---|---|---|

---

## 7. Core User Flows

### First Visit Flow

### Login / Activation Flow

### Core Usage Flow

### Payment / Purchase Flow

### Delivery / Download / Result Flow

### Admin Operation Flow

### Error and Edge-case Flow

---

## 8. Page Map

| Page | Route | Purpose | Modules | Key Actions | Data Needed | States |
|---|---|---|---|---|---|---|

---

## 9. UI / UX Specification

### Design Positioning

### Visual Keywords

### Layout Rules

### Component Style

### C-side Page Guidance

### Admin Page Guidance

### Mobile / Desktop Priority

### Required States

- Empty:
- Loading:
- Error:
- Success:
- Disabled:
- Quota exhausted:

---

## 10. Feature Specification

For each feature:

| Feature | User Story | Behavior | Input | Output | Permission | State Change | Edge Cases | Acceptance Criteria |
|---|---|---|---|---|---|---|---|---|

---

## 11. Recommended Tech Stack

### Frontend

### Backend

### Database

### Storage

### Auth

### Payment / Activation

### AI / Third-party API

### Deployment

### Why This Stack

---

## 12. Frontend Architecture

### Routes

### Components

### State Management

### Form Handling

### Error Handling

### Responsive Rules

---

## 13. Backend Architecture

### Core Services

### Auth / Permission

### Business Logic

### Rate Limit

### Logging

### Async Jobs

---

## 14. Database Schema

For each table:

| Table | Purpose | Fields | Indexes | Relationships | Status Enums |
|---|---|---|---|---|---|

---

## 15. API Design

For each API:

| Method | Path | Purpose | Auth | Request | Response | Validation | Errors | Idempotency |
|---|---|---|---|---|---|---|---|---|

---

## 16. Third-party Integrations

| Integration | Purpose | Key Config | Failure Handling | Cost/Risk |
|---|---|---|---|---|

---

## 17. Admin / Operations Design

### Admin Pages

### Operator Actions

### Logs

### Manual Overrides

---

## 18. Risk and Cost Review

| Risk | Severity | Trigger | Mitigation | Blocks MVP? |
|---|---|---|---|---|

---

## 19. Codex Implementation Plan

### Batch 1: Project Setup

- Goal:
- Scope:
- Likely files:
- Implementation notes:
- Acceptance criteria:
- Do not do:

### Batch 2: Core UI

### Batch 3: Backend and Database

### Batch 4: Core Business Flow

### Batch 5: Admin / Operations

### Batch 6: Testing and Deployment

---

## 20. Acceptance Criteria

### User Flow

### Payment / Activation

### Admin

### Security

### Cost Control

### Deployment

---

## 21. Launch Checklist

### Functionality

### Security

### Cost

### Deployment

### Commercialization

---

## 22. Final Codex Prompt

```text
You are a senior full-stack engineer.

Build this product according to the attached Product Build Spec.

Rules:
1. Do not change the product scope without asking.
2. Follow the specified tech stack and architecture.
3. Implement in small batches.
4. Start with the requested batch only.
5. After the batch, summarize what was built, what files changed, and what remains.
6. Add loading, empty, error, disabled, and success states where relevant.
7. Do not skip database schema, API validation, permission checks, or quota checks when they are in scope.
8. Use clean, maintainable code.
9. If something is ambiguous, make the smallest reasonable assumption and document it.
10. Do not add features outside the current batch.

Start with Batch 1 only.
```
```
