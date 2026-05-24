# AI Reasoning Logic

## Overview
The Coral Cloud Resorts AI agent uses Salesforce Agentforce Builder to orchestrate customer conversations, retrieve Salesforce data, validate customer identity, and automate booking workflows through structured reasoning logic.

The agent combines:
- Conversational AI
- Action orchestration
- Salesforce Flow execution
- Guardrail validation
- Subagent routing

---

# Primary Agent

## CC Service Agent

The CC Service Agent acts as the primary conversational interface between the customer and the Salesforce ecosystem.

Responsibilities:
- Handle customer conversations
- Route requests to subagents
- Maintain conversational context
- Coordinate workflow execution

---

# Subagent Architecture

## Experience Management Subagent

This subagent specializes in:
- Experience inquiries
- Session retrieval
- Customer validation
- Booking orchestration

The subagent executes actions dynamically based on customer intent.

---

# AI Action Reasoning Flow

## Step 1 — Customer Inquiry

Example:
"Tell me more about the Full Moon Beach Party."

The AI agent:
1. Detects an experience inquiry
2. Determines customer validation is required
3. Requests:
   - Email address
   - Membership number

---

# Customer Validation Logic

## Action Used
`Get Customer Details`

Purpose:
- Validate customer identity
- Retrieve Salesforce Contact record
- Prevent unauthorized booking actions

Required Inputs:
- email
- memberNumber

Output:
- Contact Salesforce record

Guardrail:
No additional actions are allowed until the customer is validated.

---

# Experience Retrieval Logic

## Action Used
`Get Experience Details`

Purpose:
- Retrieve experience details from Salesforce
- Provide grounded AI responses

Required Input:
- experienceName

Output:
- Experience__c Salesforce record

The AI agent summarizes retrieved information into conversational language for the customer.

---

# Session Retrieval Logic

## Action Used
`Get Sessions`

Purpose:
- Retrieve available sessions for a selected experience

Required Logic:
- Ask customer for preferred date if not provided
- Use Experience__c ID from Get Experience Details
- Never use plain text experience names directly

Output:
- Available session records

---

# Booking Workflow Logic

## Action Used
`Create Experience Session Booking`

Purpose:
- Create a Salesforce booking record

Required Inputs:
- Contact__c
- Session__c
- Number_of_Guests__c

Booking Workflow:
1. Customer selects session
2. AI requests number of guests
3. AI executes booking action
4. Confirmation returned to customer

---

# AI Guardrails

The AI reasoning system enforces several safeguards:

## Validation Requirements
- Customer must be verified before booking actions
- Membership verification required

## Data Integrity
- Salesforce record IDs used instead of plain names
- Structured action execution

## Conversational Controls
- Ask clarifying questions when needed
- Require session selection if multiple sessions exist

---

# Conversational AI Orchestration

The project demonstrates enterprise AI orchestration patterns:

Customer Message
↓
Intent Detection
↓
Subagent Selection
↓
Action Selection
↓
Salesforce Flow Execution
↓
Data Retrieval
↓
AI Summarization
↓
Customer Response

---

# Salesforce Components Used

- Salesforce Agentforce Builder
- Salesforce Flow
- Experience Cloud
- Embedded Messaging
- Salesforce CRM Records
- AI Subagents
- Custom Actions

---

# Key Learning Outcomes

This project strengthened understanding of:
- Enterprise AI reasoning systems
- Agent orchestration
- Conversational workflow design
- Salesforce AI implementation
- AI guardrail architecture
- Action-based reasoning models
- CRM-integrated conversational AI