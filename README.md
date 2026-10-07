# Enterprise Autonomous Incident Response & Escalation Swarm

An automated incident management and triage system built with **n8n** and **Google Gemini Chat Models**.

## Architecture & Flow
![Workflow Architecture](architecture.png)

1. **Trigger:** Incoming chat message / incident context.
2. **Classification:** SLA Classifier Agent (Gemini) classifies severity.
3. **Routing:** Routes by severity (P0 Critical, P1 High, P2/Fallback).
4. **Actions:** 
   - P0: War Room Commander -> Gmail Red Alert + Google Sheets logging.
   - P1: Ops Recovery Agent -> Ops Escalation logging.
   - P2: Auto Resolver Agent -> Resolved Inquiry archive.

## How to Import
1. Download `workflow.json`.
2. Open your n8n instance.
3. Go to **Workflows** -> **Import from File**.
4. Configure your Gemini API keys, Gmail, and Google Sheets credentials.
