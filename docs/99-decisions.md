# PortalCmsLite Product Decisions

## Product Type

PortalCmsLite is a GitHub Template Repository for creating public marketing websites for software products, SaaS platforms, and AI solution/service offerings.

It is not the real product application.

## Website Types

PortalCmsLite supports three marketing website blueprints:

1. Product Marketing Website
2. Single SaaS Marketing Website
3. AI Solutions / Holding Website

## Technology Direction

- ASP.NET Core 10
- Razor Pages
- One web project only
- SQLite with EF Core
- Server-rendered pages
- Persian RTL-first

## Architecture Decision

Use one ASP.NET Core Razor Pages project.

Do not use Clean Architecture, CQRS, microservices, or separate Domain/Application/Infrastructure projects in v1.

## Content Strategy

Database-backed:

- Articles
- Categories
- Tags
- Admin users
- Site settings
- Lead/contact form submissions
- SMTP settings
- Backup logs

File-based:

- Static pages
- Menus
- Homepage cards
- Site profile
- Landing page configuration

## Article System

Articles are stored in SQLite. Article body is Markdown rendered to HTML for public pages.

Article content strategy:

- SEO educational articles
- Tutorials
- Case studies

## Internal API

Codex/scripts can create, update, publish, and unpublish articles through an internal API protected by `X-Portal-Api-Key`.

Codex/scripts can upload article images through an internal image API.

## Image System

Article images should be validated, resized, and converted to WebP. Store uploaded images under `/wwwroot/uploads/articles/{yyyy}/{MM}/`.

## Admin Panel

Admin panel includes:

- Dashboard
- Articles
- Categories
- Tags
- Leads/reports
- Site settings
- Email/SMTP settings
- Backup

Admin panel does not manage static pages, menus, or homepage sections in v1.

## Lead Forms

PortalCmsLite v1 includes simple lead/contact forms with SQLite storage and SMTP email notification.

Supported forms:

- Contact
- Demo request
- Consultation request

No drag-and-drop form builder in v1.

## Backup

Admin can create, list, download, and delete backup ZIP files for disaster recovery.

Backup includes SQLite database, uploads, static content files, navigation files, homepage JSON files, and site profile files.

Backups must be stored outside `wwwroot`.

V1 does not include admin restore. Restore is manual and documented.

## SEO

PortalCmsLite must include technical SEO foundations:

- Clean URLs
- Meta title
- Meta description
- Canonical URL
- OpenGraph tags
- Article schema
- Sitemap
- Robots.txt
- RSS feed

## Security

Security must be simple but production-conscious:

- Hashed admin passwords
- Cookie authentication for admin
- API key for internal API
- Anti-forgery tokens on admin forms
- Upload validation
- Markdown HTML sanitization
- No secret logging

## Performance

No caching in v1.

Reason: expected size is small, around 100 articles and 10 static pages.

Keep performance simple:

- Server-rendered pages
- Minimal JavaScript
- Optimized WebP images
- Small CSS
- Pagination for articles

## Template Strategy

New websites should be created from this template, not normal GitHub forks.

Generated websites may keep PortalCmsLite as an upstream remote for controlled framework updates.

## Scope Guard

Never implement actual product application logic inside PortalCmsLite.

Do not implement dating workflows, employee monitoring workflows, LLMOps orchestration, AI pipelines, BI dashboards, complaint management workflows, customer dashboards, or payment systems here.
