# Database and API Design Rules

This file defines practical data and API design rules for lightweight products.

---

## 1. General Database Principles

Use PostgreSQL for most paid tools and small SaaS projects.

Prefer simple schemas in v0.1:

- enough to support current workflow
- enough to debug and operate
- enough to extend later
- not over-normalized

Always include:

- id
- created_at / createdAt
- updated_at / updatedAt when mutable
- status field for stateful records
- indexes for search keys

---

## 2. Common Tables

### users

Purpose: store user identity and permission state.

Common fields:

- id
- email or phone
- password_hash if password auth
- role
- status
- plan
- remaining_credits
- expires_at
- created_at
- updated_at

### products

Purpose: define sellable items or plans.

Common fields:

- id
- name
- description
- price
- credits
- duration_days
- status
- created_at
- updated_at

### orders

Purpose: track payment and fulfillment.

Common fields:

- id
- order_no
- user_id
- product_id
- amount
- currency
- status
- payment_channel
- payment_trade_no
- paid_at
- fulfilled_at
- created_at
- updated_at

Important statuses:

- pending
- paid
- fulfilled
- cancelled
- refunded
- failed

### license_keys

Purpose: card-key activation or software license.

Common fields:

- id
- key
- product_id
- status
- credits
- duration_days
- activated_by
- activated_at
- expires_at
- batch_id
- created_at

Important statuses:

- unused
- activated
- expired
- disabled

### generations / tasks

Purpose: store AI generation or processing tasks.

Common fields:

- id
- user_id
- type
- input_json
- output_json
- model_name
- status
- cost_estimate
- error_message
- created_at
- updated_at

### usage_logs

Purpose: record quota/cost related events.

Common fields:

- id
- user_id
- action
- credits_delta
- related_id
- metadata_json
- created_at

---

## 3. API Design Principles

Every API should specify:

- method
- path
- purpose
- auth requirement
- request body
- response body
- validation rules
- error cases
- idempotency requirement if money/delivery is involved

---

## 4. Common APIs

### Auth

```text
POST /api/auth/login
POST /api/auth/logout
GET /api/auth/me
```

### Generation / Core Action

```text
POST /api/generate
GET /api/generations
GET /api/generations/:id
```

### License / Activation

```text
POST /api/license/activate
GET /api/license/status
```

### Orders / Payment

```text
POST /api/orders/create
GET /api/orders/:id
POST /api/payments/{channel}/notify
```

### Admin

```text
GET /api/admin/users
GET /api/admin/orders
GET /api/admin/license-keys
POST /api/admin/license-keys/batch-create
GET /api/admin/generations
```

---

## 5. Payment and Delivery Idempotency

Any payment callback or fulfillment API must be idempotent.

Rules:

1. Check if order is already paid or fulfilled before processing.
2. Verify payment signature if using official payment channel.
3. Update order and delivery state in a transaction.
4. Never assign the same license key twice.
5. Return the expected success response to payment channel after successful processing.
6. Log abnormal callbacks.

---

## 6. Validation and Error Handling

Each API must define:

- required fields
- max length
- enum values
- file size limits
- permission check
- quota check
- rate limit
- duplicate request handling

Common error types:

- invalid_input
- unauthorized
- forbidden
- quota_exhausted
- rate_limited
- not_found
- payment_not_completed
- generation_failed
- internal_error

---

## 7. Data Safety Rules

- Do not expose API keys to the client.
- Do not store large base64 files in database or localStorage.
- Store large files in object storage.
- Store only necessary user data.
- Admin APIs must enforce role checks.
- User APIs must prevent reading other users' data.
- Money, license, and permission changes should be logged.
