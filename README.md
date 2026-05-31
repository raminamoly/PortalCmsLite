# PortalCmsLite

PortalCmsLite is a Codex-friendly ASP.NET Core Razor Pages foundation for Persian RTL public marketing websites.

It is intended to be used as a GitHub Template Repository for:

- Product marketing websites
- Single SaaS marketing websites
- AI solutions / holding websites

PortalCmsLite is **not** the real product application. Do not implement product dashboards, SaaS workflows, dating logic, employee monitoring logic, LLMOps orchestration, BI engines, payment systems, or customer portals here.

## Stack Direction

- ASP.NET Core 10
- Razor Pages
- SQLite + EF Core
- One web project only
- File-based menus, homepage cards, and static pages
- SQLite-backed articles, leads, settings, admin users, SMTP settings, and backup logs
- Persian RTL-first

## Current Phase

This repository will contain both:

1. A working website foundation.
2. Codex documentation/prompts for generating future product websites from the template.

## Important Design Rules

- Use Razor Pages, not SPA.
- Use one web project, not Clean Architecture.
- Store articles and leads in SQLite.
- Store static pages, menus, and landing cards in files.
- Keep the base foundation simple and fast.
- Do not add caching in v1.
- Do not create a page builder.
- Do not add product application logic.
