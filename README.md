<p align="center">
  <img src="src/app/icon.svg" alt="CareerForge Logo" width="80" height="80">
</p>

<h1 align="center">CareerForge</h1>

<p align="center">
  Your intelligent, self-hosted job search command center: maintain a single master profile, generate tailored resumes and cover letters for every application, and track your entire pipeline from draft to offer.
</p>

<p align="center">
  <a href="https://github.com/PrakulSmarty/Resume_Optimizier/releases/latest"><img alt="Latest Release" src="https://img.shields.io/github/v/release/PrakulSmarty/Resume_Optimizier?label=release"></a>
  <a href="https://github.com/PrakulSmarty/Resume_Optimizier/actions/workflows/image.yml"><img alt="CI Status" src="https://img.shields.io/github/actions/workflows/image.yml/badge.svg"></a>
  <a href="LICENSE"><img alt="License: AGPL-3.0" src="https://img.shields.io/badge/license-AGPL--3.0-blue"></a>
  <a href="https://github.com/PrakulSmarty/Resume_Optimizier/pkgs/container/resume_optimizier"><img alt="Docker Image" src="https://img.shields.io/badge/image-ghcr.io-2496ED?logo=docker&logoColor=white"></a>
  <img alt="Next.js 16" src="https://img.shields.io/badge/Next.js-16-000000?logo=nextdotjs">
  <img alt="PostgreSQL 18" src="https://img.shields.io/badge/PostgreSQL-18-4169E1?logo=postgresql&logoColor=white">
</p>

---

## Overview

**CareerForge** centralizes your professional history into a single, structured master profile. When you find a job you love, CareerForge reads the posting, analyzes how well your skills match, and drafts a custom-tailored resume and cover letter using **only verified facts from your profile**—preventing AI hallucination. 

Refine your documents via interactive chat, export them as professional PDFs, and track every application through a clean Kanban-style pipeline.

Designed with data ownership in mind, CareerForge runs locally or on your own server. Your private career data stays securely within your own PostgreSQL database or SQLite file, powered by the AI model of your choice (local models via Ollama/LM Studio or any OpenAI-compatible, Anthropic, or Mistral API).

---

## Core Features

- **Master Profile:** Manage your basics, skills, languages, experience, projects, education, certifications, and publications in one place. Features a built-in strength meter to ensure your profile is fully optimized.
- **Dynamic Resumes & Themes:** Choose from 12 professional themes or build your own with live previews and server-side PDF generation.
- **Job Discovery & Scoring:** Search job boards (JSearch, Adzuna, FreeHire) or import startup listings directly. Every posting is instantly scored against your profile.
- **AI-Powered Tailoring:** Paste any job description to instantly extract key requirements, view profile gaps objectively, and draft tailored application assets.
- **Chat & Refinement:** Fine-tune your resume or cover letter using an interactive chat assistant. Roll back changes or tweak specific sections effortlessly.
- **Pipeline Tracking:** Monitor your career search progress using an integrated dashboard, funnel analytics, Kanban boards, and an event calendar.
- **Optional Integrations:** 
  - **MCP Connector:** Seamlessly use CareerForge from Claude or other MCP-supported applications.
  - **Gmail & Calendar:** Send applications, track employer responses, and sync interviews directly with Google Calendar.

---

## Getting Started (Quick Run via Docker)

### 1. Configure Environment
Create a dedicated directory and set up your environment variables:
```bash
mkdir ~/careerforge && cd ~/careerforge
curl -fsSL -o compose.yml [https://raw.githubusercontent.com/PrakulSmarty/Resume_Optimizier/main/compose.production.yml](https://raw.githubusercontent.com/PrakulSmarty/Resume_Optimizier/main/compose.production.yml)
echo "POSTGRES_PASSWORD=$(openssl rand -hex 24)" > .env
echo "CAREERFORGE_SECRET=$(openssl rand -base64 32)" >> .env
