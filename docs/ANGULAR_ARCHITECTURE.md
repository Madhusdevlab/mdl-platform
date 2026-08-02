# Angular Architecture

Version: 1.0.0

Status: Draft

Last Updated: 02 August 2026

Owner: Madhu's Dev Lab

---

# Purpose

This document defines the architectural decisions, engineering principles, folder organization, and development standards for the Madhu's Dev Lab (MDL) web platform.

The goal is to establish a scalable, maintainable, and enterprise-grade Angular application that can evolve alongside the business.

---

# 1. Project Overview

The MDL Portfolio is the official web platform of Madhu's Dev Lab.

It serves as the company's digital presence, showcasing services, project spotlights, technical expertise, engineering practices, and future digital products.

The application is designed as an enterprise-grade Angular application with a strong emphasis on:

- Scalability
- Maintainability
- Performance
- Accessibility
- SEO
- Modern Angular Architecture

The platform is intentionally designed to support future expansion, including:

- Blog
- Project Spotlights
- Client Portal
- Digital Products
- SaaS Applications
- Developer Resources

---

# 2. Architecture Goals

The application architecture is designed to be:

- Scalable
- Modular
- Maintainable
- Reusable
- Testable
- Performant
- Accessible
- SEO Friendly
- Future Ready

Every architectural decision should support long-term growth rather than short-term convenience.

---

# 3. Technology Stack

| Layer            | Technology                              |
| ---------------- | --------------------------------------- |
| Framework        | Angular 20                              |
| Language         | TypeScript                              |
| Styling          | SCSS                                    |
| HTML             | HTML5                                   |
| State Management | Angular Signals                         |
| HTTP             | HttpClient                              |
| Forms            | Reactive Forms (Typed)                  |
| Icons            | Lucide Angular                          |
| Build Tool       | Angular CLI                             |
| Package Manager  | npm                                     |
| Version Control  | Git + GitHub                            |
| Deployment       | GitHub Pages (Initial), Vercel (Future) |

---

# 4. Angular Version

The project is built using Angular 20.

Key Angular features used throughout the application:

- Standalone Components
- Angular Signals
- Functional Providers
- Functional Interceptors
- Lazy Loading
- Strict TypeScript
- Modern Router APIs
- OnPush Change Detection (where applicable)

NgModules will be avoided unless required by third-party libraries.

---

# 5. Architecture Principles

The application follows these engineering principles.

## Feature First

Organize code by business feature rather than technical layer.

---

## Reusability

Reusable UI components belong inside the Shared layer.

---

## Separation of Concerns

Presentation, business logic, configuration and utilities remain independent.

---

## Single Responsibility

Each component, service and utility should have one clear responsibility.

---

## Scalability

The architecture should support future features without major restructuring.

---

## Maintainability

Code should be easy to understand by another developer.

---

## Consistency

Follow naming conventions, folder structure and coding standards across the application.

---

# 6. Folder Structure

The application follows a Feature-First Architecture.

```text
src/
│
├── app/
│   ├── core/
│   │   ├── config/
│   │   ├── constants/
│   │   ├── guards/
│   │   ├── interceptors/
│   │   ├── services/
│   │   └── tokens/
│   │
│   ├── shared/
│   │   ├── components/
│   │   ├── directives/
│   │   ├── pipes/
│   │   ├── interfaces/
│   │   ├── models/
│   │   ├── enums/
│   │   └── utils/
│   │
│   ├── features/
│   │   ├── home/
│   │   ├── services/
│   │   ├── work/
│   │   ├── about/
│   │   ├── blog/
│   │   └── contact/
│   │
│   ├── layouts/
│   │   ├── main-layout/
│   │   └── minimal-layout/
│   │
│   ├── app.config.ts
│   ├── app.routes.ts
│   └── app.ts
│
├── assets/
│   ├── fonts/
│   ├── icons/
│   ├── images/
│   ├── illustrations/
│   └── seo/
│
└── styles/
    ├── abstracts/
    ├── base/
    ├── components/
    ├── layout/
    ├── themes/
    ├── utilities/
    └── styles.scss
```

---

# 7. Routing Strategy

The application will use Angular's standalone router.

Routing principles:

- Lazy-loaded feature routes
- Route-level code splitting
- Simple URL structure
- SEO-friendly URLs
- Centralized route configuration

Initial routes:

- /
- /services
- /work
- /about
- /blog
- /contact

---

# 8. Lazy Loading

All feature pages will be lazy loaded.

Benefits:

- Faster initial load
- Smaller bundles
- Better performance
- Easier maintenance

---

# 9. State Management

State management will follow a lightweight approach.

Local UI State

- Angular Signals

Application State

- Services + Signals

No external state management library (NgRx, NGXS, Akita) will be introduced unless future business requirements justify the additional complexity.

---

# 10. Signals Strategy

Signals will be used for:

- UI State
- Loading States
- Theme Switching
- Navigation State
- Component Communication (where appropriate)

RxJS remains the preferred solution for asynchronous streams and HTTP operations.

---

# 11. API Layer

The API layer follows a service-based architecture.

Principles:

- One service per domain
- Strong typing
- DTO mapping
- Centralized error handling
- Functional HTTP Interceptors

---

# 12. Shared Components

Reusable UI components include:

- Button
- Card
- Badge
- Chip
- Input
- Textarea
- Modal
- Loader
- Section Header
- CTA Banner
- Technology Badge

Shared components should remain presentation-focused.

---

# 13. Core Services

Core services include:

- Theme Service
- Navigation Service
- SEO Service
- Meta Service
- Analytics Service (Future)
- Logger Service

These services are singletons available throughout the application.

---

# 14. Styling Strategy

Styling follows:

- SCSS
- CSS Variables
- Design Tokens
- BEM-inspired naming where appropriate
- Component-level styles
- Global utility classes only when reusable

---

# 15. Assets Organization

Assets are grouped by purpose.

- Images
- Icons
- Fonts
- Logos
- Documents
- SEO Assets

Large assets should be optimized before committing.

---

# 16. Environment Configuration

Separate environment files will be maintained for:

- Development
- Production

Environment files should contain only configuration values and never sensitive credentials.

---

# 17. Error Handling

Application-wide error handling includes:

- Functional HTTP Interceptors
- Global Error Handler
- User-friendly error messages
- Logging support (future)

Errors should fail gracefully without breaking the user experience.

---

# 18. Performance Strategy

Performance goals:

- Lazy Loading
- Optimized Images
- Tree Shaking
- Code Splitting
- Minimal Bundle Size
- OnPush Change Detection
- Lighthouse Score above 90

---

# 19. SEO Strategy

SEO implementation includes:

- Meta Tags
- Open Graph Tags
- Canonical URLs
- Structured Data (Future)
- Sitemap
- robots.txt

---

# 20. Accessibility Strategy

Accessibility standards include:

- Semantic HTML
- Keyboard Navigation
- Focus Management
- WCAG Color Contrast
- ARIA Labels
- Screen Reader Compatibility

Accessibility is considered during development, not after.

---

# 21. Deployment Strategy

Initial Deployment

- GitHub Pages

Future Deployment

- Vercel

Deployment goals:

- Automated CI/CD
- Zero-downtime deployments
- Custom Domain
- HTTPS

---

# 22. Coding Standards

Development standards:

- Standalone Components
- Strong Typing
- Avoid any
- Small Components
- Single Responsibility
- OnPush Change Detection where applicable
- Consistent Naming Conventions
- Reusable Components
- Clean Git History
- Meaningful Commit Messages

---

# 23. Architecture Decisions

| Decision                   | Reason                       |
| -------------------------- | ---------------------------- |
| Standalone Components      | Modern Angular approach      |
| Feature-First Architecture | Better scalability           |
| Angular Signals            | Lightweight state management |
| Reactive Forms             | Enterprise standard          |
| SCSS                       | Maintainable styling         |
| Lucide Icons               | Lightweight and consistent   |
| Lazy Loading               | Better performance           |

---

# 24. Out of Scope (Version 1)

The following features are intentionally excluded from Version 1:

- Authentication
- Authorization
- CMS Integration
- Internationalization (i18n)
- PWA
- Offline Support
- Backend Development
- Payment Integration

These may be introduced in future releases as the MDL platform evolves.

---

# Final Principle

Every architectural decision should answer one question:

> **"Will this still be the right decision two years from now?"**

If the answer is yes, it belongs in MDL.
