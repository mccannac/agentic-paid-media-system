# Agentic Paid Media System

## What it is

A node-by-node n8n build specification for a Google Ads agent that diagnoses performance problems and proposes fixes, with every action approved by a human.

## Problem it solves

Search campaigns waste budget quietly: rising CPA, irrelevant search terms and falling conversion rates often go unnoticed until the monthly review. Checking for them by hand across accounts is slow, and fully automated "AI optimization" is too risky to trust with budget.

## How it works

1. **Pull reports** – GAQL queries for campaign, search-term, keyword, ad and change-event data, plus optional GA4 landing-page signals.
2. **Deterministic checks** – JavaScript Code nodes calculate KPIs, detect anomalies (with minimum-volume gates), classify search terms and correlate recent account changes.
3. **Evidence pack** – findings are bundled into a structured JSON evidence pack.
4. **LLM strategist** – the model diagnoses three issues (CPA deterioration, search-term waste, conversion-rate deterioration) and proposes from five action types.
5. **Policy and risk gate** – output is validated against a schema and risk rules.
6. **Slack approval** – each proposed action is sent for human approve/reject.
7. **Execute and log** – approved actions (e.g. negative keywords, budget changes) are applied via the Google Ads API and recorded in an optimization ledger.

## Files

| File | What it is |
|---|---|
| `SEM_Agentic_Workflow_n8n_Build_Spec.md` | Full MVP spec: credentials, API config, data model, GAQL queries, node-by-node workflow, Code-node logic, evidence-pack schema, LLM prompt and output schema, approval flow, execution, acceptance criteria and roadmap |
| `LICENSE` | MIT license |

## Status

**Build spec (v1 MVP scope).** Not yet built or deployed.

*Designed by me; drafted with Claude/ChatGPT.*
