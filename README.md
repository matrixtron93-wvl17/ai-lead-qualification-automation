# AI Lead Qualification Automation

## Project Status

✅ Completed

## Overview

An AI-powered lead qualification workflow built with n8n that automatically receives, validates, analyzes, scores, routes, stores, and notifies the team about new leads.

The automation reduces manual lead qualification and ensures leads are consistently categorized based on business-defined criteria.

---

## Business Problem

Sales teams often spend time manually reviewing incoming leads, determining their quality, entering information into databases, and notifying the appropriate team members.

This automation handles those repetitive steps automatically.

---

## Solution

The workflow automatically:

1. Receives lead information through a webhook.
2. Validates required lead information.
3. Sends valid leads to an AI model for qualification.
4. Generates a lead score from 0–100.
5. Categorizes leads as HOT, WARM, or COLD.
6. Routes leads based on qualification.
7. Stores lead information and AI results in PostgreSQL.
8. Sends an email notification.
9. Returns clear responses for invalid requests and system errors.

---

## Workflow Architecture

Lead Form / API Request
        ↓
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
   ┌────┼────┐
  HOT  WARM  COLD
   └────┼────┘
        ↓
Save Lead to PostgreSQL
        ↓
Send Lead Notification

Error Handling:
- Invalid Lead → Invalid Lead Response
- AI Failure → AI Error Response
- Database Failure → Database Error Response
- Email Failure → Email Error Response

---

## AI Qualification

The AI evaluates leads using:

- Budget
- Company size
- Service fit
- Timeline / urgency
- Intent expressed in the lead message

The AI returns:

- Qualification
- Score
- Reason
- Recommended action

Example:

```json
{
  "qualification": "HOT",
  "score": 90,
  "reason": "Strong service fit and urgent implementation timeline.",
  "recommended_action": "Contact the lead promptly and schedule a discovery call."
}