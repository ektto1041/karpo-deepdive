# AI Agent Instructions for Karpo Deepdive Blog

This document serves as the ground truth for AI agents working on this project.

## 1. Project Overview
**Name**: Karpo Deepdive
**Type**: Personal Tech Blog / Knowledge Base
**Goal**: A clean, high-performance blog to share in-depth technical articles and tutorials.
**Structure**: Monorepo using **Turborepo** and **pnpm**.

## 2. Technology Stack
- **Language**: TypeScript (Strict Mode)
- **Package Manager**: pnpm (Workspaces)
- **Monorepo Tool**: Turborepo
- **Version Management**: pnpm Catalog
- **Linting & Formatting**: Biome

## 3. Architecture & Directory Structure
Standard Monorepo Structure:

```
/
├── apps/                 # Application packages
│   └── web/              # Main web application
├── packages/             # Shared libraries
│   ├── config/           # Shared configurations (eslint, tsconfig)
│   └── lib/              # Shared logic/utilities
├── turbo.json            # Turborepo configuration
├── biome.json            # Biome configuration (Lint/Format)
├── pnpm-workspace.yaml   # Workspace definition
└── package.json          # Root scripts
```

## 4. Coding Standards
### General
- **DRY (Don't Repeat Yourself)**: Extract reusable logic into shared packages or utilities.
- **KISS (Keep It Simple, Stupid)**: Avoid over-engineering.
- **Linting/Formatting**: Use **Biome**. Run `pnpm check` before committing.

### TypeScript
- **Strict Typing**: Avoid `any`. Define interfaces/types for all data structures.
- **Explicit Returns**: Clearly define return types for complex functions.

## 5. Best Practices for This Project
- **SEO is Crucial**: Ensure semantic HTML (`main`, `article`, `h1`-`h6`, `nav`, `footer`).
- **Accessibility**: Ensure all interactive elements are accessible.

## 6. Monorepo Workflow
- **Adding Dependencies**: `pnpm add <pkg> --filter <appName>`
- **Running Dev Server**: `pnpm dev` (runs all apps in parallel via Turbo)
- **Building**: `pnpm build` (caches results via Turbo)
- **Lint/Format**: `pnpm check` (runs Biome check)

## 7. Workflow
1. **Analyze**: Understand the requirements.
2. **Plan**: If complex, draft a plan in `implementation_plan.md`.
3. **Implement**: Write usage code.
4. **Verify**: Check functionality.
5. **한국어**: 코드를 제외한 모든 답변은 한국어로 작성한다.
