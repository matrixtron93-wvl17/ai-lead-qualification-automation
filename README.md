# AI Lead Qualification & CRM Automation

An end-to-end AI-powered lead qualification and CRM automation workflow built with n8n, PostgreSQL, and an LLM.

The system receives lead information, validates the data, uses AI to qualify the lead, routes the lead based on qualification, stores the lead in PostgreSQL, updates a CRM record, tracks interactions, and sends an automated notification.

---

## Project Overview

This automation is designed for businesses that receive leads through forms, websites, or other systems and need to automatically evaluate and organize those leads.

Instead of manually reviewing every lead, the workflow automatically:

- Receives lead information
- Validates incoming data
- Uses AI to evaluate the lead
- Assigns a qualification
- Generates a lead score
- Provides an AI-generated reason
- Recommends the next action
- Routes HOT, WARM, and COLD leads
- Stores lead data in PostgreSQL
- Creates or updates a CRM record
- Tracks total interactions
- Sends an automated lead notification

---

## Workflow Architecture

```text
Receive Lead
      ↓
Prepare Lead Data
      ↓
Validate Lead
      ↓
AI Lead Qualification
      ↓
Parse AI Result
      ↓
Route by Qualification
      ↓
Save Lead to PostgreSQL
      ↓
Upsert Lead CRM
      ↓
Send Lead Notification
      ↓
Respond to Webhook