# Agent Configuration

## Overview

This document outlines the complete configuration of the Coral Cloud Resorts AI Service Agent built using Salesforce Agentforce Builder.

The project includes:
- Main service agent configuration
- AI subagent configuration
- Action orchestration
- Salesforce Flow integrations
- Conversational AI instructions
- Embedded customer support deployment

---

# Main Service Agent

## Agent Name
CC Service Agent

## Platform
Salesforce Agentforce Builder

## Agent Type
Service Agent

## Purpose
The CC Service Agent acts as the primary customer-facing conversational AI assistant for Coral Cloud Resorts.

The agent helps customers:
- Learn about resort experiences
- Validate membership information
- Retrieve available sessions
- Book experiences
- Navigate resort services

---

# Assigned User

## Agent User
EinsteinServiceAgent User

## Purpose
The assigned user controls:
- Agent permissions
- Salesforce access
- Flow execution capabilities
- CRM data access

This ensures the agent can securely interact with Salesforce resources.

---

# Agent Description

You are a customer service representative, helping our guests make reservations, update bookings, and navigate all that Coral Cloud Resorts has to offer.

---

# Subagent Configuration

## Subagent Name
Experience Management

## Description
This subagent addresses customer inquiries and issues related to booking experiences at Coral Cloud Resorts, including making reservations, modifying session bookings, and answering queries about experience details.

---

# Purpose of the Subagent

The Experience Management subagent specializes in:
- Experience-related conversations
- Session retrieval
- Booking workflows
- Customer validation
- Action execution

The subagent improves:
- AI specialization
- Workflow organization
- Action orchestration
- Conversational accuracy

---

# Actions Configured

## 1. Get Experience Details

### Purpose
Retrieve Salesforce experience details for customer inquiries.

### Reference Action Type
Flow

### Reference Action
Get Experience Details

### Input Configuration
| Input | Configuration |
|---|---|
| experienceName | Require Input to execute action |

### Output Configuration
| Output | Configuration |
|---|---|
| experienceRecord | Show in conversation |

---

## 2. Get Customer Details

### Purpose
Validate customer identity and retrieve Salesforce contact records.

### Reference Action Type
Flow

### Reference Action
Get Customer Details

### Input Configuration
| Input | Configuration |
|---|---|
| email | Require Input to execute action |
| memberNumber | Require Input to execute action |

### Output Configuration
| Output | Configuration |
|---|---|
| contact | Show in conversation |

---

## 3. Get Sessions

### Purpose
Retrieve available sessions for selected experiences.

### Source
Added from Asset Library

### Functionality
- Retrieve session records
- Filter by experience
- Support booking workflows

---

## 4. Create Experience Session Booking

### Purpose
Create Salesforce booking records for customers.

### Source
Added from Asset Library

### Required Inputs
- Contact__c
- Session__c
- Number_of_Guests__c

### Functionality
- Create booking records
- Associate customer with session
- Store guest counts
- Return booking confirmation

---

# AI Instruction Configuration

## Subagent Instruction Logic

The AI instructions define:
- Customer verification requirements
- Action execution sequence
- Session retrieval rules
- Booking workflows
- Conversational guardrails

---

# Instruction Workflow

## Customer Inquiry Flow

1. Customer asks about an experience
2. AI requests:
   - Email
   - Membership number
3. AI validates customer
4. AI retrieves experience details
5. AI summarizes information conversationally

---

# Session Retrieval Workflow

1. AI retrieves Experience__c record
2. AI requests preferred date if missing
3. AI uses Experience__c ID
4. AI retrieves available sessions
5. AI presents sessions to customer

---

# Booking Workflow

1. Customer selects session
2. AI retrieves Session__c ID
3. AI requests number of guests
4. AI executes booking action
5. AI confirms reservation

---

# AI Guardrails

## Validation Guardrails
- Customer validation required before actions
- Membership verification enforced

## Data Integrity Guardrails
- Salesforce IDs required
- Structured action execution enforced

## Conversational Guardrails
- Clarifying questions required
- Session selection required when multiple sessions exist

---

# Builder Views Used

## Canvas View
Used for:
- Natural language editing
- Visual configuration
- Instruction management

---

## Script View
Used for:
- Direct instruction editing
- Action reference updates
- Advanced orchestration logic

---

# Agent Lifecycle Configuration

## Commit Version
The agent configuration was committed into a deployable runtime version.

## Activate
The agent was activated to:
- Enable live execution
- Support preview testing
- Connect to customer-facing channels

---

# Testing Configuration

## Preview Mode
Live Test Mode

## Test Scenarios
- Experience inquiry
- Customer validation
- Session retrieval
- Booking workflow

---

# Deployment Connections

## Embedded Service Deployment
ESA Web Deployment

## Flow Routing
Route to ESA Flow

## Experience Cloud Site
coral-cloud

## Embedded Component
Embedded Messaging

---

# Final Architecture

Customer
↓
Embedded Messaging
↓
CC Service Agent
↓
Experience Management Subagent
↓
Salesforce Actions
↓
CRM Data + Booking Records

---

# Technologies Used

- Salesforce Agentforce Builder
- Salesforce Flow
- Embedded Messaging
- Experience Cloud
- Salesforce CRM
- AI Subagents
- Conversational AI
- Flow Actions

---

# Key Configuration Outcomes

Successfully configured:
- Enterprise conversational AI agent
- AI-driven booking workflows
- CRM-connected customer validation
- Multi-action orchestration
- Embedded customer support assistant
- Structured AI reasoning system