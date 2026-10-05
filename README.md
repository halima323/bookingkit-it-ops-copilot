# bookingkit IT Ops & AI Agent Copilot (demo)

An n8n workflow that handles IT onboarding, offboarding and support tickets in one pipeline. This is an independent demonstration project that uses **synthetic data only** (14 fictional requests). It is not affiliated with or endorsed by any company.

## What it does
- **Three request types, one pipeline:** 4 onboarding, 3 offboarding and 7 IT ticket requests in the sample data.
- **Onboarding and offboarding:** rule-based checklists and licence logic by role.
- **IT tickets:** keyword triage first, then optional AI classification.
- **AI guardrails:** the AI can only raise urgency (never lower it), can only suggest a knowledge-base article that exists, and any "access granted" or "issue resolved" wording is removed before a person sees it.
- **Outputs:** an HTML IT operations dashboard (readiness, ticket queue, licence utilisation, automation-opportunity backlog, AI-enablement gaps) plus draft Slack, Jira and Google Workspace payloads.
- **Human approval:** nothing is sent externally until the push setting is switched on, and every action is meant to be approved by a person.

## Files
- `bookingkit-it-ops-ai-copilot.json`: the n8n workflow (26 working nodes plus 4 note nodes).

## How to run it
1. In n8n, choose **Import from file** and select the JSON file.
2. Click **Execute workflow** on the manual trigger, or open the dashboard webhook URL.
3. All rules (role checklists, licence inventory, knowledge-base articles, ticket categories, AI prompt, endpoints) are in the node named **2. Load CONFIG**.

## Tools
n8n, JavaScript (Code nodes), Slack, Google Workspace and Jira (draft integrations), an OpenAI-compatible LLM API (optional).

Built by Halima Khatoon.
