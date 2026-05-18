# Codex Execution Rules

Diamond Build Skill must produce a development plan that Codex can execute in small batches.

---

## 1. Codex should not receive the entire dream version

Give Codex a clear v0.1 scope.

Bad:

```text
Build a complete platform with user system, payment, AI, admin, reseller, analytics, and resource marketplace.
```

Good:

```text
Build Batch 1 only: initialize Next.js project, configure Tailwind, create layout, create homepage and tool page placeholders. Do not implement payment or AI yet.
```

---

## 2. Batch Structure

Recommended batches:

### Batch 1: Project Setup

- initialize project
- install dependencies
- configure environment variables
- create base layout
- create basic routes
- create shared components

### Batch 2: Core UI

- homepage
- core tool page
- result preview
- pricing/activation section if needed
- loading/empty/error states

### Batch 3: Backend and Database

- Prisma schema
- database connection
- core API routes
- validation
- basic logs

### Batch 4: Core Business Flow

- AI generation or core processing
- quota/activation check
- order or license flow if needed
- save records

### Batch 5: Admin / Operations

- admin auth
- user/order/license/resource management
- generation/task logs
- manual adjustments

### Batch 6: Testing and Deployment

- test core flows
- fix edge cases
- mobile/desktop polish
- environment variables
- deployment checklist

---

## 3. Each Batch Must Include

- goal
- exact scope
- likely files
- implementation rules
- acceptance criteria
- what not to do in this batch

---

## 4. Codex Prompt Rules

Every Codex prompt should include:

1. role: senior full-stack engineer
2. stack constraints
3. scope boundaries
4. batch number
5. files likely involved
6. acceptance criteria
7. instruction to summarize changed files
8. instruction not to expand scope

---

## 5. Default Codex Prompt

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

---

## 6. Review Questions Before Sending to Codex

- Is the current batch small enough?
- Are non-goals clear?
- Are files/routes/API names clear?
- Are states and errors specified?
- Are acceptance criteria testable?
- Are external services mocked or real in this batch?
- Does Codex know what not to build?
