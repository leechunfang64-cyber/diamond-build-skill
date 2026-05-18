# UI Style Defaults

Diamond Build Skill should not leave UI vague. Every Product Build Spec must include a clear UI/UX direction.

---

## 1. C-side Commercial Tool Style

Default positioning:

```text
高级、干净、轻 SaaS 感、可信、商业化、克制，不要廉价模板感，不要过度 AI 味。
```

Visual keywords:

- clean
- premium
- focused
- card-based
- high contrast CTA
- calm spacing
- clear hierarchy
- subtle shadows
- restrained gradients
- trustworthy copy

Recommended structure:

- top navigation
- hero section
- one-sentence value proposition
- primary CTA
- product preview or demo card
- 3-5 key benefits
- workflow steps
- pricing or activation section
- FAQ

---

## 2. Tool Page Layout

For most generation or processing tools:

```text
Left side: input/configuration
Right side: preview/output/result
Top: current status/quota/account
Bottom: core actions
```

Important states:

- empty state: show example result or guide
- loading state: clear progress text
- error state: explain what happened and what user can do
- success state: show result actions
- quota exhausted state: guide to activation/payment

---

## 3. Admin Dashboard Style

Default positioning:

```text
效率优先，清晰、密度高、可搜索、可筛选、可批量操作。
```

Recommended stack:

- Ant Design 5
- data tables
- status tags
- filter forms
- batch actions
- detail drawer
- operation logs

Admin pages should include:

- list page
- detail page or drawer
- create/edit modal
- status filters
- keyword search
- export/import if operationally needed

Avoid:

- fancy animations
- oversized cards
- low-density layouts
- marketing-style admin pages

---

## 4. Trust Details

For paid tools, include trust signals:

- clear pricing
- clear quota or usage limits
- refund/service explanation if needed
- contact/support path
- examples of output
- visible activation or membership status
- clear error messages

Trust is more important than decoration.

---

## 5. Mobile and Desktop Priority

Default:

- C-side marketing pages: mobile-friendly
- core tool pages: desktop-first if input/output are complex
- admin pages: desktop-first

If the product is for teachers, office workers, PPT users, resource managers, or operators, desktop-first is usually better.

If the product is for Xiaohongshu creators, consumers, or social media users, mobile adaptation should be stronger.

---

## 6. UI Anti-patterns

Avoid:

- unclear CTA
- too many gradients
- fake futuristic AI visuals
- overly long forms
- results hidden below the fold
- no example output
- no empty/loading/error states
- admin without search/filter
- mobile pages that break the core workflow

---

## 7. UI Spec Requirements

Every build spec should include:

- design positioning
- page layout
- component style
- major states
- example copy direction
- desktop/mobile priority
- admin style if applicable

A UI spec that only says “modern and clean” is not enough.
