# Deployment Process

## Overview

This document outlines the deployment lifecycle of the Coral Cloud Resorts AI Service Agent built using Salesforce Agentforce Builder.

The deployment process includes:
- Agent configuration
- Subagent setup
- Action orchestration
- AI instruction configuration
- Flow routing
- Embedded messaging deployment
- Experience Cloud integration
- Live testing

---

# Phase 1 — Agent Creation

## Create Main Service Agent

Platform:
- Salesforce Agentforce Builder

Agent Name:
- CC Service Agent

Purpose:
The primary service agent acts as the customer-facing conversational AI assistant responsible for:
- Experience inquiries
- Session booking
- Customer validation
- Workflow orchestration

Configuration:
- Assigned user:
  `EinsteinServiceAgent User`

---

# Phase 2 — Subagent Configuration

## Experience Management Subagent

Purpose:
Specialized AI subagent responsible for:
- Experience detail retrieval
- Session lookup
- Booking workflows
- Customer assistance

Subagent Description:
This subagent addresses customer inquiries and issues related to booking experiences at Coral Cloud Resorts, including making reservations, modifying session bookings, and answering queries about experience details.

---

# Phase 3 — Action Configuration

## Custom Actions Created

### Get Experience Details
Purpose:
Retrieve Salesforce experience information.

Reference Action Type:
- Flow

Inputs:
- experienceName

Outputs:
- experienceRecord

---

### Get Customer Details
Purpose:
Validate customer information.

Reference Action Type:
- Flow

Inputs:
- email
- memberNumber

Outputs:
- contact

---

## Asset Library Actions Added

### Get Sessions
Purpose:
Retrieve available sessions for experiences.

### Create Experience Session Booking
Purpose:
Create booking records in Salesforce.

---

# Phase 4 — AI Reasoning Configuration

## Subagent Instructions

The AI instructions define:
- Customer validation requirements
- Action execution sequence
- Session retrieval rules
- Booking workflow logic
- Conversational guardrails

Key orchestration logic:
1. Validate customer first
2. Retrieve experience details
3. Retrieve sessions
4. Request session selection
5. Request guest count
6. Create booking
7. Return confirmation

---

# Phase 5 — Version Control and Activation

## Commit Version

The configured agent was committed into a deployable version within Agentforce Builder.

Version Actions:
- Commit Version
- Error scanning and validation
- AI instruction validation

---

## Activate Agent

After successful validation:
- Agent activated
- Service agent published
- Runtime orchestration enabled

Activation enables:
- Live AI reasoning
- Action execution
- Customer interaction
- Embedded deployment readiness

---

# Phase 6 — Preview Testing

## Agentforce Preview Testing

Testing was performed using:
- Live Test Mode

Test Scenario:
1. Customer requested experience details
2. Agent requested customer verification
3. Agent retrieved Salesforce records
4. Agent retrieved available sessions
5. Agent created booking record
6. Agent returned booking confirmation

Validation Results:
- Actions executed successfully
- Customer validation worked
- Session retrieval worked
- Booking workflow completed successfully

---

# Phase 7 — Embedded Service Deployment

## ESA Web Deployment

Location:
Setup → Embedded Service Deployments

Deployment:
- ESA Web Deployment

Actions:
- Republished deployment
- Enabled latest agent updates

Purpose:
Expose conversational AI functionality to customer-facing channels.

---

# Phase 8 — Flow Routing Configuration

## Route to ESA Flow

Flow Updated:
- Route to ESA

Routing Configuration:
Route To:
- Agentforce Service Agent

Assigned Agent:
- CC Service Agent

Purpose:
Route customer conversations directly to the deployed AI service agent.

---

# Phase 9 — Experience Cloud Integration

## Embedded Messaging Component

Platform:
- Experience Builder

Site:
- coral-cloud

Component Added:
- Embedded Messaging

Placement:
- Homepage near “Book an Experience of a Lifetime”

Purpose:
Enable live conversational AI directly on the website.

---

# Phase 10 — Live Website Testing

## Customer Simulation Testing

Test Prompt:
"Can you let me know about the Underground Cave Exploration?"

Validation:
- Messaging launched successfully
- Agent responded correctly
- Customer validation executed
- Experience details retrieved
- Booking workflow operational

---

# Deployment Architecture

Customer Website
↓
Embedded Messaging
↓
Route to ESA Flow
↓
CC Service Agent
↓
Experience Management Subagent
↓
Salesforce Actions
↓
CRM Data + Booking Records

---

# Deployment Outcomes

Successfully deployed:
- Enterprise conversational AI agent
- AI-driven booking workflow
- CRM-integrated customer validation
- Experience Cloud embedded assistant
- Action-based orchestration system

---

# Technologies Used

- Salesforce Agentforce Builder
- Salesforce Flow
- Experience Cloud
- Embedded Messaging
- Salesforce CRM
- AI Subagents
- Conversational AI
- Flow Actions

---

# Lessons Learned

Key deployment insights:
- AI guardrails are critical for workflow integrity
- Action orchestration improves reliability
- Structured reasoning improves conversational accuracy
- Embedded messaging enables seamless customer interaction
- Salesforce Flow integration provides scalable automation