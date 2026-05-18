# Build Principles

These principles guide Diamond Build Skill when converting a validated demand into a product development blueprint.

---

## 1. Build the smallest sellable product

Do not aim for the smallest technically usable product only. Aim for the smallest product that can test payment, delivery, and user value.

A first version should answer:

- Can users understand the value quickly?
- Can users complete the core action?
- Can users receive the promised result?
- Can the operator charge money or verify willingness to pay?
- Can the operator deliver and handle basic support?

---

## 2. Delivery model comes before feature list

Before designing features, identify what the user is buying.

Possible delivery models:

- online tool result
- generated document
- downloadable file
- membership access
- card-key activation
- manual service
- software license
- batch processing
- private-domain service package

Different delivery models imply different technical structures.

---

## 3. Monetization model comes before permission system

Do not design permissions blindly.

First identify how the product will charge:

- free trial
- one-time payment
- credit package
- membership duration
- card key
- manual payment + manual activation
- subscription
- reseller/agent
- service fee

Then design permissions around that monetization model.

---

## 4. Manual first is acceptable

For early MVPs, manual steps are not shameful. They can reduce development time and risk.

Acceptable manual steps in v0.1:

- manual payment confirmation
- manual card-key sending
- manual user permission adjustment
- manual resource upload
- manual handling of failed orders
- manual customer support

Automate only after real usage proves the flow is worth automating.

---

## 5. Admin is for operations, not vanity

Build admin features only when they support:

- user management
- order/payment management
- card-key or license management
- content/resource management
- generation logs
- quota adjustment
- support and refund handling
- cost monitoring
- risk control

Do not build dashboards just because dashboards look professional.

---

## 6. Feature priority must be tied to evidence

A feature should be P0 only if it is required for:

- core user value
- payment verification
- delivery
- permission control
- operational safety
- cost control

Everything else should be P1, P2, or Non-goal.

---

## 7. One core workflow first

A fast MVP should focus on one core workflow:

```text
user enters → understands value → performs action → gets result → pays or activates → operator can see record
```

Do not design multiple workflows before the first one works.

---

## 8. Prefer familiar stacks

The user wants speed. Do not choose a new stack just because it is fashionable.

Prefer stacks the user can repeatedly reuse:

- Next.js + React + TypeScript
- Tailwind CSS + shadcn/ui
- Ant Design 5 for admin
- Supabase PostgreSQL + Prisma
- Upstash Redis
- WordPress for resource/download sites
- Vercel for first deployment
- VPS + Nginx + Docker/Baota when domestic deployment, ICP, callback stability, or cost control matter

---

## 9. AI cost must be designed from day one

Any AI product must include:

- request limits
- free quota limits
- paid quota logic
- input length control
- retry handling
- model selection logic
- generation logs
- approximate cost tracking

AI cost leakage can quietly kill margins.

---

## 10. Good specs reduce Codex rework

A good Product Build Spec must define:

- exact pages
- exact routes
- exact user flows
- exact data fields
- exact APIs
- exact states
- exact non-goals
- exact acceptance criteria

If Codex has to guess too much, the spec is not ready.
