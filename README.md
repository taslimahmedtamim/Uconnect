# UConnect

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Process](https://img.shields.io/badge/process-Agile-blue)](#sdlc--process-agile)
[![Platform](https://img.shields.io/badge/platform-Web%20first%20%E2%86%92%20Mobile%20next-purple)](#development-plan-web-first-mobile-next)
[![Tech Stack](https://img.shields.io/badge/stack-React%20%7C%20Node%20%7C%20Python%20%7C%20Postgres%20%7C%20OpenAI-orange)](#tech-stack)

UConnect is an AI-driven university ecosystem that connects students, teachers, and recruiters to collaborate on projects, form balanced teams, build verified portfolios, generate polished resumes, and discover jobs/internships — starting with a web-first build.

Core value: Turn academic work into verifiable career assets and accelerate the path from learning → experience → employment.

---

## Table of Contents

- [Vision & Summary](#vision--summary)
- [Development Plan (Web First → Mobile Next)](#development-plan-web-first-mobile-next)
- [SDLC & Process (Agile)](#sdlc--process-agile)
- [Modules at a Glance](#modules-at-a-glance)
- [Key Features](#key-features)
  - [Core Modules](#core-modules)
  - [Career & Employability](#career--employability)
  - [AI & Analytics](#ai--analytics)
  - [Collaboration & Community](#collaboration--community)
  - [Engagement & Gamification](#engagement--gamification)
- [Architecture Overview](#architecture-overview)
- [Tech Stack](#tech-stack)
- [Monorepo Structure](#monorepo-structure)
- [Getting Started (Web)](#getting-started-web)
  - [Prerequisites](#prerequisites)
  - [Environment Variables](#environment-variables)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
  - [AI Services Setup](#ai-services-setup)
  - [Running Tests, Lint, Format](#running-tests-lint-format)
- [Mobile App Plan](#mobile-app-plan)
- [Data Model & Concepts](#data-model--concepts)
- [API & Integrations (Overview)](#api--integrations-overview)
- [Security, Privacy & Ethics](#security-privacy--ethics)
- [Demo & Pitch Flow](#demo--pitch-flow)
- [Success Metrics](#success-metrics)
- [Contributing](#contributing)
- [License](#license)
- [Team & Contact](#team--contact)
- [Appendix: Full Feature Index](#appendix-full-feature-index)

---

## Vision & Summary

- Project Name: UConnect
- Vision: An AI-driven university ecosystem connecting students, teachers, and industry — automating team formation, learning, portfolio building, resume generation, and job/internship discovery.
- Who it serves: Students, faculty/mentors, recruiters/companies.
- Outcomes:
  - Faster, fairer team formation and mentorship.
  - Verified portfolios and certificates as credible hiring signals.
  - Personalized career paths and job matches that reflect true skills.

---

## Development Plan (Web First → Mobile Next)

We will prioritize a web-based release first, then build the mobile app.

- Web first:
  - Focus on core flows: auth, profiles, project/team formation, portfolio, resume generation, opportunity discovery.
  - Ship quickly to validate with students/faculty; iterate based on feedback.
- Mobile next:
  - Build a dedicated mobile app after the web release stabilizes.
  - Target tech: React Native to maximize reuse with the React web stack.
  - Mobile priorities: notifications, quick apply, chat, task updates, mentor sessions.

---

## SDLC & Process (Agile)

- Framework: Agile (Scrum/Kanban hybrid depending on team size and cadence).
- Cadence:
  - Iterative delivery in short cycles.
  - Lightweight planning, continuous refinement, and frequent releases.
- Ceremonies:
  - Planning and backlog refinement
  - Daily standups
  - Review/demo
  - Retrospective with actionable improvements
- Backlog & Prioritization:
  - Value-first prioritization; capture user feedback from web release to inform subsequent iterations and mobile scope.
- Definition of Done:
  - Coded, reviewed, tested, documented (user-facing notes where needed), and deployed.
- Branching & CI/CD:
  - Trunk-based or short-lived feature branches.
  - GitHub Actions for tests/lint/build; preview deployments for frontend; automatic checks before merge.

---

## Modules at a Glance

- Profiles & Portfolio: Rich, verifiable profiles with skills, projects, endorsements, and shareable mini-sites.
- Team Formation & Project Hub: Create calls for projects, form balanced teams, track progress and milestones.
- Career & Resume: AI-generated resumes and job matching with skill-gap insights and roadmaps.
- AI Services: Matching engine, NLP job parsing, interview coach, and analytics.
- Community & Collaboration: Realtime chat, help boards, issue conversion, and mentor marketplace.
- Reputation & Scoring: U-Score based on outcomes, contributions, reviews, and timeliness.

---

## Key Features

### Core Modules

- Smart Collaboration Engine (AI “Brain”): Learns from skills, projects, GPA, interests, outcomes, and feedback to improve matches over time.
  - Continuously updates weights to reflect recency, reliability, and mentor endorsements.
- Intelligent Team Formation: Auto-creates balanced teams (skills, experience, availability) with teacher constraints (handpick, prefer seniors, cross-dept).
  - Supports hard constraints (must-have) and soft preferences (nice-to-have).
- Adaptive Skill Profiling: Profiles update from workshops, projects, certifications, mentor feedback. Skill weights adjust by recency, frequency, endorsement.
  - Generates a transparent skill graph per user with evidence links.
- Comprehensive Profiles (students/faculty): Projects, U-Score, skill graph, badges, verified internships, shareable mini-site (uconnect.me/username).
  - Public/private toggles for fields to control recruiter visibility.
- Opportunity Discovery Hub: Projects, hackathons, internships, and events ranked by match score and proximity.
  - Filter by stack, timeline, location, team size, and difficulty.
- Teacher–Student Collaboration: Project calls, team approvals, mentor assignment, evaluation forms, private faculty dashboards.
  - Rubrics with comment threads and exportable grading reports.
- UConnect Communication Space: Realtime chat, discussion rooms, file sharing, activity timeline.
  - Topic channels per project and DM support with attachments.
- Smart Project Lifecycle Tracker: Tasks, deadlines, auto-milestones, progress analytics, AI task-splitting suggestions.
  - Burnup/burndown charts; deadline nudges via notifications.
- U-Score (Reputation & Skill Scoring): Combines outcomes, peer reviews, mentor feedback, contribution tracking.
  - Guardrails ensure explainability and allow faculty overrides.
- Cross-Department Bridge: Easily form interdisciplinary teams (e.g., CSE + Design + BBA).
  - Weighted diversity score to encourage balanced teams.
- AI-Curated Project Repository: Archive of completed projects with metadata, outcomes, repo links, templates.
  - Search by stack, tags, complexity, and success metrics.

### Career & Employability

- U-Resume (AI-Generated Resume/CV): Converts profile into professional resumes. Multiple templates (Corporate/Modern/Academic), export (PDF/DOCX/LinkedIn), AI-polished bullets.
  - Bullet rewriting emphasizes impact, metrics, and action verbs.
- U-Hire / CareerConnect: Aggregates jobs (LinkedIn, Google Jobs, local portals), match percentage, skill gaps, geolocation filters (near me, commute radius, remote).
  - Track applications and reminders in one place.
- U-SkillMap (Skill Gap Analyzer): Compares profile to job requirements, recommends prioritized learning paths and time-to-readiness estimates.
  - Links to resources and project ideas to close gaps.
- Apply-with-UConnect (1-click Apply): Use generated resume + prefilled cover letter, track application statuses.
  - Optional customizations per job with AI assistance.
- Recruiter Dashboard: Filter candidates by U-Score, skills, verified projects; post micro-internships/challenges; track submissions.
  - Shortlists with evidence-backed candidate cards.
- Verified Certificates: Mentor/company verifications with optional blockchain anchoring.
  - Tamper-resistant proofs attach to portfolio items.

Career Path Advisor & Personalized Roadmaps:
- Career Path Recommendation: Suggest roles (Backend, Data, UX, PM) with confidence and rationale.
- Adaptive Roadmaps: Step-by-step skills, resources, projects, milestones, mentor suggestions; auto-adjust with progress and labor market changes.
- Compare Paths: Visual overlaps, effort, demand; pivot recommendations (e.g., Frontend → Full-Stack).
- Resource/Micro-Credential Integrations: Link to MOOCs, playlists, books; add certificates to profile.
- Mentor Matching per Roadmap, Progress Tracking, Assessments, Salary Estimates (optional), Exportable Plans.

### AI & Analytics

- Skill Graph & Knowledge Map: Neo4j graph of skills, prerequisites, related jobs; visual explorer.
- Hybrid Recommendation Engine: Content-based + collaborative filtering with peer success signals.
- NLP Job Parsing & Matching: BERT/sentence-transformers to parse JDs and compute similarity.
- AI Career Predictor: Predicts probable career tracks using alumni and trajectory data.
- Performance & Growth Analytics: Skill growth curves, project success rates, team contribution, benchmarks.
- AI Interview Coach: Mock interviews (text/voice), recorded feedback and scoring.

### Collaboration & Community

- Smart Task Assistant & Auto-Scheduler: Break down tasks, effort estimates, deadlines, Google Calendar sync.
- Voice & Video Collaboration: WebRTC/Jitsi, voice queries/commands.
- Peer Mentorship & Community: Mentor matching, office hours, help forums.
- Cross-University Mode: Joint competitions, shared project calls, industry challenges.

Community Project Sharing & Open Collaboration:
- Share Repo Links & Request Help: Public help board (bug-help, feature-request, mentor-review, docs). Auto metadata extraction (language, issues, README summary).
- Issue & Collaboration Workflow: Convert posts into Help Tickets, assign volunteers, deadlines, threads. GitHub OAuth for issues/PRs and status sync.
- Visibility of Senior Projects: Public archive (with consent) by dept/year/stack/outcomes; upgrade requests; licensing clarity.
- Mentor & Reviewer Marketplace: List availability with tags; book review/debug sessions.
- Contributor Reputation & Incentives: Badges, U-Score boosts; track commits, PRs, issues, mentorship hours.
- Discovery & Search: Full-text index of READMEs/issues/tags; “Find Flask projects with beginner issues”.
- Governance & Copyright: Owner permissions, license templates (MIT/Apache/CC), consent, moderation tools.
- Educational Tie-ins: Convert collaboration tasks to assessed labs/capstones with rubrics.
- Micro-Internships (Optional): Paid upgrades/sponsored tasks.

### Engagement & Gamification

- Badges & Achievements, Leaderboards & Challenges, Streaks & XP.

---

## Architecture Overview

- Frontend SPA (React) handles UI, routing, and OAuth flows. Web is the primary client initially.
- Backend API (REST/GraphQL) manages users, projects, teams, scoring, notifications.
- Realtime (Socket.io/Firebase) for chat, presence, and live updates.
- AI Services (Python microservices) for recommendations, resume generation, matching, and interview coach.
- Datastores: Postgres (primary), MongoDB (optional docs), Neo4j (skill graph), Vector DB (FAISS/Pinecone), Elasticsearch (text search), Redis (queues/cache), S3/Cloud Storage.
- Integrations: OAuth/SSO, GitHub sync, job portals, maps/geolocation.
- Mobile: React Native app consuming the same APIs; push notifications via FCM/APNs; deep links to resources.

---

## Tech Stack

- Frontend (Web):
  - React, Tailwind CSS, shadcn/ui, React Query, React Router, Chart.js/Recharts
  - Hosting: Vercel (or Netlify)
- Backend:
  - Node.js + Express (or Django alternative)
  - ORM/migrations: Prisma (Node) or Django ORM (Python)
- AI/ML:
  - Python, scikit-learn, TensorFlow/PyTorch, sentence-transformers, spaCy, OpenAI API
- Databases:
  - PostgreSQL (primary), MongoDB (optional), Neo4j (graph)
- Search/Matching:
  - Elasticsearch (text search) and/or FAISS/Pinecone (semantic)
- Realtime:
  - Socket.io or Firebase
- Storage:
  - AWS S3 or Firebase Storage
- Auth:
  - OAuth2 (Google, GitHub), University SSO, JWT
- Hosting:
  - Vercel (frontend), Render/Heroku/AWS/GCP (backend)
- Jobs & Maps:
  - LinkedIn Jobs, Google Jobs, local portals (APIs/scraping), Google Maps
- Mobile (Planned):
  - React Native, React Query, Expo Router or React Navigation, FCM/APNs, CodePush/OTA

---

## Monorepo Structure

```
UConnect/
├── backend/          # Node/Express or Django (choose one baseline)
│   ├── src/
│   ├── prisma/       # or migration tooling of choice
│   ├── tests/
│   └── package.json  # or requirements.txt for Django
├── frontend/         # React + Tailwind + shadcn/ui (Web)
│   ├── src/
│   ├── public/
│   ├── tests/
│   └── package.json
├── mobile/           # React Native app (planned)
│   ├── app/
│   ├── src/
│   ├── tests/
│   └── package.json
├── ai/               # Python microservices for AI/recs/resume/interview coach
│   ├── services/
│   ├── models/
│   ├── tests/
│   └── requirements.txt
├── docs/             # Architecture, ADRs, API docs, diagrams
├── tests/            # End-to-end, integration (e.g., Playwright/Cypress)
└── README.md
```

---

## Getting Started (Web)

### Prerequisites

- Node.js 18+
- npm or yarn
- Python 3.9+
- PostgreSQL 14+
- (Optional) Redis for queues
- Git

### Environment Variables

Create .env files for backend, frontend, and AI services.

Backend (.env)
```
PORT=4000
NODE_ENV=development
DATABASE_URL=postgresql://user:password@localhost:5432/uconnect
JWT_SECRET=replace_me
# OAuth
GITHUB_CLIENT_ID=...
GITHUB_CLIENT_SECRET=...
GOOGLE_CLIENT_ID=...
GOOGLE_CLIENT_SECRET=...
# AI/Vector/Search
OPENAI_API_KEY=...
PINECONE_API_KEY=...
PINECONE_ENV=...
ELASTICSEARCH_URL=http://localhost:9200
# Queue/Cache
REDIS_URL=redis://localhost:6379
# Storage
S3_BUCKET=your-s3-bucket
S3_REGION=ap-south-1
S3_ACCESS_KEY=...
S3_SECRET_KEY=...
```

Frontend (.env.local)
```
VITE_API_URL=http://localhost:4000/api
VITE_OAUTH_REDIRECT_URL=http://localhost:3000/auth/callback
VITE_APP_NAME=UConnect
```

AI Services (.env)
```
OPENAI_API_KEY=...
FAISS_INDEX_PATH=.data/faiss.index
PINECONE_API_KEY=...
PINECONE_ENV=...
```

### Backend Setup

Node.js + Express (example)
```
cd backend
npm install
# If using Prisma (or your ORM):
npx prisma migrate dev --name init
npm run dev
```

Django (alternative)
```
cd backend
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver 0.0.0.0:4000
```

### Frontend Setup

```
cd frontend
npm install
npm start
# open http://localhost:3000
```

### AI Services Setup

```
cd ai
pip install -r requirements.txt
# Start service(s), e.g. FastAPI/Flask entrypoint:
python run_service.py
```

### Running Tests, Lint, Format

- Backend tests: `npm test` (Node) or `pytest` (Python)
- Frontend tests: `npm test`
- Lint: `npm run lint`
- Format: `npm run format`

---

## Mobile App Plan

- Tech: React Native (Expo or bare) to reuse business logic and UI patterns from the web where sensible.
- API: Same REST/GraphQL endpoints; shared types via OpenAPI/Swagger or codegen to reduce drift.
- Auth: OAuth with deep links (App/Universal Links), secure token storage.
- Features (initial):
  - Push notifications for deadlines, chat mentions, mentor feedback.
  - Quick actions: apply to jobs, update task status, check-in for sessions.
  - Lightweight profile edits and resume export links.
- Offline-first (select screens): local cache with background sync for tasks/messages.
- Release: Closed beta after the web release stabilizes; iterate via OTA updates (Expo/CodePush).

---

## Data Model & Concepts

Core entities:
- User (student, teacher, recruiter)
- Profile (skills, GPA, achievements, endorsements)
- Project (repo link, description, outcomes)
- Team (members, roles, approvals)
- Opportunity (job, internship)
- MentorMatch (sessions, feedback)
- U-Score (reputation & performance metrics)
- Roadmap (career path, milestones, resources)

Illustrative ER (simplified)
```mermaid
erDiagram
  USER ||--o{ PROFILE : has
  USER ||--o{ TEAM_MEMBER : participates
  TEAM ||--o{ TEAM_MEMBER : includes
  USER ||--o{ PROJECT : owns
  PROJECT ||--o{ TASK : contains
  PROJECT ||--o{ FEEDBACK : receives
  USER ||--o{ FEEDBACK : gives
  USER ||--o{ OPPORTUNITY_APPLICATION : applies
  OPPORTUNITY ||--o{ OPPORTUNITY_APPLICATION : tracks
  USER ||--o{ CERTIFICATE : earns
  USER ||--o{ ROADMAP : follows
  ROADMAP ||--o{ MILESTONE : contains
```

U-Score considerations:
- Inputs: project outcomes, peer reviews, mentor feedback, code contributions, on-time delivery.
- Guardrails: explainability, bias checks, manual overrides for faculty.

---

## API & Integrations (Overview)

Representative endpoints (example; subject to change):
- Auth: `POST /api/auth/register`, `POST /api/auth/login`, `GET /api/auth/oauth/callback`
- Users/Profiles: `GET /api/users/:id`, `PUT /api/users/:id`, `GET /api/users/:id/score`
- Projects/Teams: `POST /api/projects`, `GET /api/projects`, `POST /api/teams/suggest`, `POST /api/projects/:id/tasks`
- Career/Resume: `POST /api/resume/generate`, `GET /api/opportunities?near=...&skills=...`
- Community: `POST /api/help-posts`, `POST /api/help-posts/:id/convert`, `POST /api/github/issues`
- Roadmaps: `POST /api/career-paths/recommend`, `POST /api/roadmaps/generate`, `PUT /api/roadmaps/:id/progress`

Integrations:
- GitHub OAuth + repo import, create issues/PRs, contribution sync.
- Job feeds (LinkedIn, Google Jobs, local portals), Google Maps geolocation.
- OpenAI/LLMs for summaries, matching, interview coach.

Documentation:
- Plan to expose OpenAPI/Swagger at `/api/docs`.

---

## Security, Privacy & Ethics

- Data Privacy Controls: Clear settings for public/recruiter/private fields.
- Explainable Recommendations: “Matched because of Python, ML project X, teamwork rating.”
- Secure Auth & Verification: SSO/OAuth, JWT, 2FA, encrypted storage, audit trails.
- Bias & Fairness: Regular audits on matching/scoring; appeal workflows; teacher overrides.
- Certificates & Integrity: Optional blockchain anchoring for tamper-resistance.
- Compliance: Respect site terms for job aggregation; licensing and consent for public projects.

---

## Demo & Pitch Flow

1. Opening Problem (20s): Student struggles to find teammates/internships.
2. Live Flow (90s): Profile → Auto team formation → Project summary → Auto resume → Job matches near me → Apply.
3. Technical Slide (60s): Architecture + AI matching.
4. Impact (30s): Faster placements, fair teams, verified portfolios.
5. Closing (20s): Scale to more universities; national hiring funnel.

---

## Success Metrics

- Team formation satisfaction rates after projects.
- U-Score correlation with job placement.
- Count of verified internships/certificates.
- Average time-to-hire for U-Hire users.
- Engagement (DAU/retention/messages per project).

---

## Contributing

We welcome contributions!

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit: `git commit -m "Add your-feature"`
4. Push: `git push origin feature/your-feature`
5. Open a Pull Request

Guidelines:
- Follow lint and code style
- Add tests for new features
- Small, focused PRs with clear descriptions
- Respect licensing and consent for shared projects

Consider adding:
- CONTRIBUTING.md
- CODE_OF_CONDUCT.md
- SECURITY.md
- .env.example
- CI (GitHub Actions) for lint/test/build

---

## License

MIT License — see [LICENSE](LICENSE).

---

## Team & Contact

| Member                | Profession     | Gmail                          | GitHub                                                    |
|-----------------------|----------------|--------------------------------|-----------------------------------------------------------|
| Taslim Ahmed Tamim    | Student        | taslimahmedtamim4u@gmail.com   | [taslimahmedtamim](https://github.com/taslimahmedtamim)   |
| Salman Kabir Sany     | Student        | salmankabirsany@gmail.com      | [salmankabirsany](https://github.com/salmankabirsany)     |
| Majharul Islam        | Student        | majharul.cs@gmail.com          | [MrMajharul](https://github.com/MrMajharul)               |

For bug reports/feature requests, please open an issue.

---

## Appendix: Full Feature Index

This README integrates the consolidated feature specification. For a complete serial listing across Core, Career, Analytics, Collaboration, Gamification, Security, UX, Integration, Plan, and Demo …

- Core Modules (11)
- Career & Employability (6) + Career Path Advisor (10)
- AI & Analytics (6)
- Collaboration & Productivity (4) + Community/Open Collaboration (9)
- Engagement & Gamification (3)
- Security, Privacy & Trust (4)
- UX/Frontend (3)
- Integration & Tech Stack (11)
- Demo & Pitch Strategy (5 steps)
- Success Metrics (5)
- Stretch Features (5)
- Ethics & Fairness (3)
