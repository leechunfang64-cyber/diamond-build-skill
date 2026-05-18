# Product Pattern Library

This library maps common product patterns to recommended first-version development plans.

---

## 1. AI Text Generator

### Examples

- 小红书标题生成器
- 教案生成器
- 简历优化器
- 朋友圈文案生成器
- 销售话术生成器

### First-version shape

Web tool with a clear input form and generated output preview.

### P0 features

- input form
- prompt assembly
- AI generation endpoint
- result preview
- copy/download
- rate limit
- usage log

### P1 features

- login
- generation history
- card-key activation
- paid quota
- admin log viewer

### Avoid in v0.1

- template marketplace
- multi-user teams
- advanced analytics
- complex prompt editor
- multi-model routing unless needed

### Default stack

Next.js + shadcn/ui + Route Handlers + Upstash Redis + Supabase/Prisma if persistence is needed.

---

## 2. AI Design / Cover / Poster Tool

### Examples

- 小红书封面生成器
- 活动海报生成器
- 商品卡片生成器
- AI 充值卡片生成器

### First-version shape

Web tool with template-driven generation or prompt-assisted generation.

### P0 features

- choose template or style
- input text/content
- generate preview
- edit key text fields
- export image
- basic watermark/brand settings if commercial

### P1 features

- saved templates
- user history
- paid export
- batch generation

### Avoid in v0.1

- full Figma-like editor
- complex layer system
- real-time collaboration
- custom font management unless needed

### Key risk

Design tools easily overexpand. Keep first version template-driven.

---

## 3. File Processing / Document Tool

### Examples

- PPT 二创工具
- PDF 转换工具
- 批量图片处理工具
- Word/PPT 资料重组工具

### First-version shape

Choose web or desktop based on file privacy, size, and processing complexity.

### P0 features

- upload or local file select
- task configuration
- processing flow
- progress status
- result download
- error handling

### P1 features

- task history
- batch processing
- paid quota
- user account

### Avoid in v0.1

- multi-format support if one format proves demand
- complex editor
- cloud storage library
- multi-user collaboration

### Key risk

Large files, storage, bandwidth, timeout, and user privacy.

---

## 4. Resource / Download Site

### Examples

- 教务资料站
- PPT 模板站
- 课件资源站
- 素材资源站

### First-version shape

WordPress first unless the product requires strongly custom interaction.

### P0 features

- resource listing
- category/search
- product detail page
- paid download or membership download
- file storage and download permission
- basic admin upload

### P1 features

- VIP membership
- single-file purchase
- affiliate/reseller
- recommendation lists
- user favorites

### Avoid in v0.1

- complex custom SaaS
- self-developed CMS if WordPress can handle it
- advanced recommendation engine

### Key risk

Storage/bandwidth cost and copyright/resource compliance.

---

## 5. Auto Delivery / Card-key Platform

### Examples

- 自动发卡平台
- 账号卡密销售
- 软件激活码系统
- 虚拟商品交付后台

### First-version shape

Web platform with simple C-side purchase/activation and admin inventory management.

### P0 features

- product list
- order creation
- payment or manual payment status
- license/key inventory
- key assignment
- delivery result page
- admin product/order/key management

### P1 features

- payment callback
- agent/reseller
- batch import/export
- inventory warnings
- refund handling

### Avoid in v0.1

- complex reseller hierarchy
- multi-tenant SaaS
- coupon system
- advanced finance analytics

### Key risk

Payment callback idempotency, duplicate delivery, frozen funds, and customer disputes.

---

## 6. Private-domain Delivery Tool

### Examples

- 私域客户资料交付工具
- 课程配套资料开通系统
- 会员权益管理工具
- 售后答疑记录工具

### First-version shape

Internal admin + simple user access page.

### P0 features

- customer records
- access status
- manual activation
- delivery resource link
- usage/interaction notes
- admin search/filter

### P1 features

- automated notifications
- payment integration
- customer self-service portal
- renewal reminders

### Avoid in v0.1

- complex CRM
- sales pipeline board
- multi-agent commissions unless already needed

### Key risk

Operator usability matters more than fancy UI.

---

## 7. Browser Extension

### Use when

- the value appears inside another website
- user workflow depends on page context
- copy/paste friction is high

### P0 features

- content script
- popup UI
- minimal settings
- one clear action
- result insertion/copy

### Avoid in v0.1

- many target websites
- complex background automation
- risky scraping behavior

### Key risk

Platform policy, extension permissions, and website changes.

---

## 8. Mini Program

### Use when

- users are strongly WeChat-native
- mobile-first usage is necessary
- existing channel requires mini program

### Avoid as first version when

- web can test demand faster
- payment and review create delay
- product requires rapid iteration

### First-version recommendation

Use web first unless WeChat-native usage is the core advantage.
