# Default Tech Stacks

Use this file to choose the simplest reliable stack for the product being built.

---

## 1. Pure Front-end Small Tool

Use when:

- no login
- no payment
- no backend data persistence
- no sensitive API key
- user can complete the task in browser

Examples:

- calculators
- text formatters
- simple prompt templates
- JSON / CSV helper tools
- local preview tools

Recommended stack:

```text
Vite or Next.js
React
TypeScript
Tailwind CSS
localStorage if needed
Vercel or Cloudflare Pages
```

Avoid:

- database
- auth
- heavy backend
- admin panel

---

## 2. AI Web Tool

Use when:

- user enters text or files
- system calls AI API
- user receives generated output
- usage should be limited or monetized

Examples:

- 小红书标题生成器
- AI 教案生成器
- AI 简历优化工具
- AI PPT 大纲生成器
- Prompt 生成器

Recommended stack:

```text
Next.js App Router
React
TypeScript
Tailwind CSS
shadcn/ui
Next.js Route Handlers
Upstash Redis for rate limit
Supabase PostgreSQL + Prisma if users, credits, or history are needed
```

AI API rules:

- API keys must stay server-side
- add rate limits
- log generation records
- control input length
- track approximate cost
- handle timeout and failed responses

---

## 3. Paid Tool with Users, Credits, Orders, or Card Keys

Use when:

- user needs paid access
- product needs quota or credits
- card-key activation is used
- admin needs to manage users/orders/licenses

Recommended stack:

```text
Next.js App Router
React
TypeScript
Tailwind CSS
shadcn/ui for C-side
Ant Design 5 for admin
Supabase PostgreSQL
Prisma
Custom JWT or simple auth
Upstash Redis
Alipay / WeChat / manual payment / card-key activation based on stage
Vercel first, VPS later if needed
```

Core tables usually include:

- users
- products
- orders
- license_keys
- usage_logs
- generations or tasks

---

## 4. Resource Site / Download Membership Site

Use when:

- core value is content/resource download
- users want ready-made files
- interactions are simple
- speed to market matters more than custom UX

Examples:

- 教务资料站
- PPT 模板站
- 素材资源站
- 课程资料下载站

Recommended fast stack:

```text
WordPress
Paid download / membership plugin
Commercial resource-site theme
Object storage
Manual or plugin-based payment
```

Recommended custom stack only when:

- resource access logic is strongly custom
- product includes deep tools
- WordPress cannot support the business model

Custom stack:

```text
Next.js
Supabase PostgreSQL
Prisma
Object storage
Permission-controlled download links
Admin dashboard
```

---

## 5. Auto Card-key Platform

Use when:

- user buys activation codes
- system needs inventory of keys
- delivery is automatic or semi-automatic
- admin needs to manage orders and keys

Recommended stack:

```text
Next.js App Router
React
TypeScript
Ant Design 5 admin
Supabase PostgreSQL
Prisma
Upstash Redis
Custom JWT
Payment callback with idempotency
```

Critical rules:

- never assign the same key twice
- order processing must be idempotent
- use transaction for payment success + key assignment
- keep manual override ability in admin
- log all status changes

---

## 6. Desktop File-processing App

Use when:

- user processes local files
- privacy matters
- upload is inconvenient
- file processing is heavy
- users accept installation

Examples:

- PPT 二次原创
- local image batch processing
- local document converter

Recommended stack:

```text
Tauri or Electron
React UI
Node/Python backend logic if needed
Server-side license activation if commercial
Local storage for task history
```

Avoid for first version when:

- user just needs quick online experience
- install friction is too high
- payment and delivery can be tested with web version

---

## 7. Admin Dashboard

Use when:

- there are orders/users/licenses/resources/logs
- operator needs to search, filter, adjust, export, or troubleshoot

Recommended stack:

```text
Ant Design 5
Next.js admin routes
Server-side permission checks
Searchable tables
Status filters
Batch operations
Audit logs for money/permission/delivery actions
```

Admin should prioritize efficiency, not visual flourish.
