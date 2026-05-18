# Risk and Scope Rules

This file helps prevent overbuilding and missed risks.

---

## 1. Scope Control Rules

### Rule 1: One main workflow first

A v0.1 product should have one dominant workflow.

Examples:

```text
input → generate → preview → copy/download
```

```text
buy → activate → use → view quota
```

```text
browse resource → pay/activate → download
```

If the spec contains many equal workflows, it is likely overbuilt.

---

### Rule 2: P0 must be brutally small

P0 features must be required for:

- core value
- payment or activation
- delivery
- permission control
- operator visibility
- cost control

If a feature is only “nice”, move it to P1/P2.

---

### Rule 3: Explicit non-goals are mandatory

Every Product Build Spec must list what not to build.

Common non-goals:

- reseller system
- subscription billing
- multi-tenant architecture
- complex analytics
- template marketplace
- mobile app
- multi-language support
- team collaboration
- advanced permissions
- custom CMS

---

### Rule 4: Do not build automation before validation

If the operator can manually handle the first 10-50 users, manual handling may be better than automation.

Automate when:

- manual work blocks sales
- error rate becomes high
- user wait time hurts conversion
- operational cost is clearly rising

---

## 2. Risk Review Dimensions

Every build spec must review these risks.

### Payment risk

Questions:

- Is payment official or third-party?
- Can money be frozen or delayed?
- Is callback reliable?
- Is order processing idempotent?
- Is refund handling defined?

Mitigation:

- use official channel when possible
- keep manual reconciliation ability
- log all payment events
- add idempotency
- do not expose negotiation/compensation language in product records

---

### Delivery risk

Questions:

- Can the product be delivered automatically?
- What happens if delivery fails?
- Can admin retry delivery?
- Can user see delivery status?

Mitigation:

- add delivery status
- admin retry action
- delivery logs
- fallback manual delivery

---

### AI cost risk

Questions:

- Is there a free quota?
- Can users abuse generation?
- Is input length controlled?
- Is model cost tracked?
- Are failed calls retried safely?

Mitigation:

- rate limit
- quota check before generation
- input length cap
- usage logs
- paid credit deduction
- cache repeated results if appropriate

---

### Storage/bandwidth risk

Questions:

- Are files large?
- Are downloads frequent?
- Who pays egress?
- Are files stored safely?

Mitigation:

- object storage
- signed download URLs
- file size limits
- avoid base64 in database
- monitor bandwidth

---

### Content/copyright risk

Questions:

- Does product handle copyrighted material?
- Are resources legally owned?
- Are outputs likely to copy protected content?
- Are platform rules involved?

Mitigation:

- avoid explicit infringement flows
- add terms and user responsibility notice
- keep content source records
- prefer original/templates owned by operator

---

### Customer-service risk

Questions:

- Will users misunderstand what they bought?
- Is quota/duration clear?
- Can user recover from failure?
- Is support path visible?

Mitigation:

- clear pricing and quota
- clear activation status
- FAQ
- admin logs
- refund/dispute records

---

### Technical complexity risk

Questions:

- Is the product trying to do too many things?
- Does the stack require unfamiliar infra?
- Are integrations fragile?
- Are async tasks needed?

Mitigation:

- reduce P0 scope
- use known stack
- avoid unnecessary services
- add a phased plan

---

## 3. MVP Blocking Rule

A risk blocks MVP only if it prevents:

- user from receiving the core result
- operator from collecting or verifying payment
- operator from fulfilling the purchase
- basic legal/platform safety
- cost control

Otherwise, list it as a monitored risk rather than delaying the MVP.
