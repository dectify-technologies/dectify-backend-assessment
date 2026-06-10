DECTIFY Backend Engineering Assessment

⏰ Submission Deadline

📅 12 June 2026 (Friday) — 2:00 PM IST

⚠️ You have 24 hours from the time of receiving this assessment to complete and submit your solution.

⸻

Backend Intern Technical Assessment

Build a scalable backend service for lead management, scoring, authentication, and data processing.

⸻
📚 **Quick Links**

- [Overview](#-overview)
- [Business Context](#-business-context)
- [Approved Technologies](#-approved-technologies)
- [Required Tasks](#-required-tasks)
- [Dataset](#-dataset)
- [Dataset Schema](#-dataset-schema)
- [Scoring Specification](#-scoring-specification)
- [Design Requirements](#-design-requirements)
- [Deliverables](#-deliverables)
- [Bonus Tasks](#-bonus-tasks)
- [Evaluation Criteria](#-evaluation-criteria)
- [Submission Instructions](#-submission-instructions)

⸻

# 📖 Overview

At DECTIFY, backend systems power mission-critical workflows.

This assessment evaluates your ability to design, build, test, and document a production-grade backend service.

You will build a Lead Management & Scoring API that:

* Imports lead data
* Calculates lead scores
* Exposes REST APIs
* Supports filtering and pagination
* Implements authentication
* Includes automated tests

⸻

# 🌍 Business Context

At DECTIFY, lead quality drives everything downstream.

Lead scores influence which prospects receive callbacks, which enter automated nurture workflows, and which are deprioritized.

Your task is to build the service that powers those decisions by ingesting leads, scoring them, and exposing clean APIs for downstream systems.

Examples of downstream consumers:

* Sales Dashboard
* CRM Platform
* Notification Service
* Lead Management System

⸻

⚠️ Important

You may use AI tools (ChatGPT, Claude, Gemini, etc.) for assistance.

However, you must fully understand your implementation and be able to explain your code during any follow-up discussion.

Neatness, structure, and clarity of thinking matter as much as functionality.

⸻

# 🛠 Approved Technologies

Python

* FastAPI
* Flask
* Django

Node.js

* Express
* Fastify
* NestJS

TypeScript is encouraged for Node.js implementations.

You may use any open-source libraries or frameworks. Please cite any significant libraries used.

⸻

# 🎯 Required Tasks

1. Lead Management API

Build a REST API exposing CRUD operations:

* Create Lead
* Read Lead
* Update Lead
* Delete Lead
* List Leads

⸻

2. Bulk Import

Create an endpoint that imports:

sample_leads.csv

into your database.

⸻

3. Lead Scoring

Implement the scoring logic exactly as specified below.

Each lead must receive a score between 0 and 100.

⸻

4. Filtering, Sorting & Pagination

Implement:

Filtering

* Score Range
* Lead Source
* Date Range

Sorting

* Ascending
* Descending

Pagination

* Page Number
* Page Size

Endpoint Example:

GET /leads

⸻

5. Validation

Return appropriate HTTP status codes where applicable:

* 200
* 201
* 400
* 404
* 422
* 500

⸻

6. Authentication

Implement API Key Authentication using:

X-API-Key

Bonus:

* JWT Authentication

⸻

7. Unit Testing

Write meaningful tests covering:

* Scoring Logic
* Missing Data
* Budget Boundary Cases
* Validation Scenarios
* Edge Cases

⸻

8. Documentation

Provide:

* Setup Instructions
* Environment Variables
* Run Commands
* Example API Requests

Include at least:

* 3–5 sample curl requests

⸻

# 📂 Dataset

Provided File:

sample_leads.csv

Contains approximately 200 lead records.

⸻

📋 Dataset Schema

Field	Type	Notes
id	int	Unique identifier
name	string	Full name
email	string	Contact email
phone	string	+91 format
source	string	Referral / Google / Facebook / Walk-in / Other
budget_inr	int	Buyer budget in INR
location	string	City + locality
property_type	string	1BHK / 2BHK / Villa / Plot etc.
inquiry_date	date	YYYY-MM-DD
message	string	Free-text inquiry note
status	string	new / contacted / qualified / negotiating / closed

⸻

# 📊 Scoring Specification

Every lead must receive a composite score between 0 and 100.

The implementation should be:

* Correct
* Configurable
* Testable
* Maintainable

⸻

Composite Score Formula

score =
0.40 × budget_fit
+
0.30 × engagement
+
0.30 × source_quality

Final score must:

* Fall between 0 and 100
* Be returned as an integer

⸻

1. Budget Fit

Target Budget Range:

₹50,00,000 – ₹2,00,00,000

Rules:

* Within range → 100
* Below ₹25,00,000 → 0
* Above ₹3,00,00,000 → 0
* Linear decay outside the preferred range
* Missing or invalid values → 50

⸻

2. Engagement

Recency Component

* Within last 7 days → 80
* Linearly decay over 60 days
* Older than 60 days → 0

Message Bonus

* Add +20 if message exists and is non-empty

Maximum engagement score:

100

⸻

3. Source Quality

Source	Score
Referral	100
Google	80
Walk-in	70
Facebook	60
Other	40

Unknown values should default to:

40

⸻

# ⚙️ Design Requirements

The following must be configurable without modifying business logic:

* Score Weights
* Budget Thresholds
* Source Quality Mapping

Acceptable approaches:

* Environment Variables
* Configuration Files
* Constants Modules
* Dependency Injection

Important

A clean separation between configuration and business logic is one of the strongest evaluation signals in this assessment.

Avoid scattering hardcoded values throughout the application.

⸻

# 📦 Deliverables

Your submission must include:

* Public GitHub Repository
* Source Code
* README.md
* Unit Tests
* Sample API Requests
* Design Report

⸻

Design Report

Include a short report (300–500 words) explaining:

* Architecture decisions
* Design trade-offs
* Missing data handling
* Future improvements
* Testing approach

⸻

# ⭐ Bonus Tasks

The following are optional but strongly encouraged:

* Dockerfile
* Docker Compose
* OpenAPI / Swagger Documentation
* Rate Limiting
* Live Deployment (Railway, Render, Fly.io, etc.)
* PostgreSQL with Migrations
* GitHub Actions CI/CD
* JWT Authentication with Refresh Tokens
* Fault-Tolerant Bulk Import
* Per-row Failure Reporting
* Loom Walkthrough (3–5 minutes)

⸻

# 🏆 Evaluation Criteria

Area	What We Evaluate
Technical Correctness	Does the API work end-to-end?
Code Quality	Readable, modular, maintainable code
Results & Tests	Meaningful tests and edge case coverage
Problem Understanding	Design choices and trade-offs
Creativity	Additional improvements and features

⸻

# 📤 Submission Instructions

1. Complete the assessment.
2. Push your code to a public GitHub repository.
3. Include all required deliverables.
4. Ensure your README is complete and accurate.
5. Submit the repository link before the deadline.

⸻

Good Luck!

We look forward to seeing how you think, design, and build.

**— DECTIFY Recruitment Te
