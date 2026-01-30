# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

- **Client:** Aim High Electrical Services
- **Website:** https://aimhighelectricalservices.com
- **Industry:** Electrical Services (Residential)
- **Status:** Landing Page Live
- **GitHub:** https://github.com/jsprad1/aimhighelectrical
- **Vercel (Live):** https://aimhighelectrical.vercel.app

> **Full Details:** See `01_DISCOVERY/01-COMPANY-ANALYSIS.md` for complete company information, services, and SWOT analysis.

## Commands

| Command | Action |
|---------|--------|
| `research` | Run full company research via web and update all .md files |
| `research [section]` | Research specific section (company, brand, competitors, personas) |
| `update docs` | Refresh all documentation with latest findings |
| `create landing page` | Generate/regenerate the landing page HTML |
| `audit` | Check which documents are incomplete |
| `status` | Show current project status and completion percentage |
| `create workspace "[name]"` | Create client folder structure (invokes `skills/client-workspace.md`) |

## Agent Team

A virtual marketing agency team is available in `.claude/agents/`. Use `/agents` to view and manage them.

### Team Structure

```
                 @creative-director (Boss)
                         │
    ┌──────────┬─────────┼─────────┬──────────┐
    │          │         │         │          │
@researcher @strategist @copywriter @developer @analyst
    │          │         │         │          │
    └──────────┴─────────┴─────────┴──────────┘
                         │
               @campaign-manager (Execution)
                         │
                  @qc-reviewer (Final Gate)
                         │
               @status-tracker (Always Updates Status)
```

### Agent Commands

| Command | Description |
|---------|-------------|
| `@creative-director [task]` | Boss analyzes task, creates plan, delegates to specialists |
| `@researcher [task]` | Company/competitor/audience research |
| `@strategist [task]` | Positioning, messaging, campaign strategy |
| `@copywriter [task]` | Website copy, emails, ads, social content |
| `@developer [task]` | Landing pages, HTML/CSS, tracking setup |
| `@analyst [task]` | Reports, KPIs, data analysis |
| `@campaign-manager [task]` | Campaign coordination, QA, checklists |
| `@qc-reviewer [task]` | Final quality check before any client release |
| `@status-tracker [update]` | **ALWAYS call after completing work** — updates PROJECT-STATUS.md |

### Critical: Status Tracking

**After ANY work is completed, call `@status-tracker` to update the project status.**

The `@status-tracker` agent maintains `00_ADMIN/PROJECT-STATUS.md` — the single source of truth for all project status.

### How It Works

1. **For complex tasks:** Use `@creative-director` — it will analyze and delegate
2. **For specific tasks:** Go directly to the specialist agent
3. **Agents use workspace folders:** Each knows where to read/write files
4. **Handoffs are documented:** Agents pass context when work transfers

## Architecture

```
aimhighelectrical/
├── 00_ADMIN/          → Contracts, invoices, meeting notes, PROJECT-STATUS.md
├── 01_DISCOVERY/      → Research, questionnaires, audits, strategy docs
├── 02_BRAND/          → Logos, colors, typography, guidelines, templates
├── 03_CONTENT/        → Website copy, email, social, blog, ads
├── 04_DESIGN/         → Wireframes, mockups, graphics, print materials
├── 05_DEVELOPMENT/    → Website files, landing pages, technical docs
├── 06_CAMPAIGNS/      → Active marketing campaigns with briefs & results
├── 07_ANALYTICS/      → Reports, dashboards, benchmarks, insights
├── 08_DELIVERABLES/   → Final client handoffs and exports
├── 09_ARCHIVE/        → Completed/superseded work
├── skills/            → AI workflow skills
├── landing-page/      → index.html - the completed landing page (deployed to Vercel)
├── vercel.json        → Vercel deployment config (outputDirectory: landing-page)
└── .gitignore         → Git ignore rules
```

## Research Documents

| Document | Purpose |
|----------|---------|
| `01_DISCOVERY/01-COMPANY-ANALYSIS.md` | SWOT, services, differentiators, contact info |
| `02_BRAND/02-BRAND-STYLE-GUIDE.md` | Colors, fonts, voice, UI components |
| `00_ADMIN/03-PROJECT-FOLDER-STRUCTURE.md` | Full folder structure with checklist |
| `03_CONTENT/04-LANDING-PAGE-COPY.md` | Headlines, pain points, FAQs, CTAs |
| `01_DISCOVERY/05-COMPETITOR-ANALYSIS.md` | Local/industry competitor analysis |
| `01_DISCOVERY/06-SALES-PROPOSAL-TEMPLATE.md` | Service packages and pricing |
| `04_DESIGN/07-WIREFRAME-STRUCTURE.md` | Page sections with ASCII wireframes |
| `01_DISCOVERY/08-TARGET-AUDIENCE-PERSONAS.md` | Target customer personas |

## Skills

The `skills/client-workspace.md` skill creates professional marketing agency folder structures. Invoke with "create workspace for [client]".

---

## Retell Demo Configuration

> Configure these values to enable `/retell-demo` deployment for this client.

| Setting | Value | Notes |
|---------|-------|-------|
| `ghl_location_id` | `YOUR_LOCATION_ID` | GoHighLevel location ID |
| `retell_phone_number` | `+1XXXXXXXXXX` | Must be verified in Retell |
| `brand_color` | `#046bd2` | Primary color (hex) |
| `logo_url` | | Optional - leave empty for text-only header |
| `header_title` | `Try Our AI Voice Agent` | Optional custom title |
| `header_subtitle` | `Experience a personalized AI demo in under 60 seconds` | Optional |

### Deployment Status

| Resource | Status | URL/ID |
|----------|--------|--------|
| Demo Widget | Not Deployed | - |
| n8n Workflow | Not Created | - |
| Webhook | - | - |
