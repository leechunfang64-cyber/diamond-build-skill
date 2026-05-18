# Codex Batch Plan Template

Use this template to turn a Product Build Spec into executable coding-agent tasks.

---

## Batch 1: Project Setup

### Goal

Initialize the project and create the base structure.

### Scope

- initialize framework
- install dependencies
- configure TypeScript
- configure Tailwind/shadcn/Ant Design if needed
- create route structure
- create base layout
- create environment variable examples

### Likely Files

- package.json
- tsconfig.json
- tailwind.config.ts
- app/layout.tsx
- app/page.tsx
- components/*
- lib/*
- .env.example

### Acceptance Criteria

- project starts locally
- homepage loads
- base layout works
- no business logic implemented yet

### Do Not Do

- no payment
- no AI call
- no database business logic
- no admin complexity

---

## Batch 2: Core UI

### Goal

Build the visible user-facing flow without final backend integration.

### Scope

- homepage
- tool page
- input form
- result preview layout
- pricing/activation section if needed
- loading/empty/error/success states

### Acceptance Criteria

- user can understand product value
- user can fill the form
- mock result can be displayed
- UI matches the design direction

### Do Not Do

- no real AI integration unless explicitly required
- no payment callback
- no advanced admin

---

## Batch 3: Backend and Database

### Goal

Create data models and core APIs.

### Scope

- Prisma schema
- database connection
- core API routes
- validation
- logging
- basic auth if in scope

### Acceptance Criteria

- migration can run
- API validates input
- records can be created/read
- errors are handled clearly

---

## Batch 4: Core Business Flow

### Goal

Connect UI, backend, AI/core processing, quota, and delivery.

### Scope

- real generation or processing
- permission/quota check
- record saving
- result delivery
- activation or payment status check if needed

### Acceptance Criteria

- user can complete the core workflow end to end
- quota is enforced
- failed calls do not break the page
- result is saved or delivered correctly

---

## Batch 5: Admin / Operations

### Goal

Build only the admin features needed to operate v0.1.

### Scope

- admin login/permission
- user list
- order/license/task list
- detail drawer
- manual status adjustment if needed
- logs

### Acceptance Criteria

- operator can search and filter records
- operator can troubleshoot common failures
- permission checks protect admin APIs

---

## Batch 6: Testing, Polish, Deployment

### Goal

Prepare MVP for real user testing.

### Scope

- test all core flows
- fix edge cases
- mobile/desktop polish
- environment variable setup
- deployment checklist
- basic monitoring/logs

### Acceptance Criteria

- production build succeeds
- environment variables documented
- core user flow works after deployment
- no API key exposed on client
- launch checklist completed
