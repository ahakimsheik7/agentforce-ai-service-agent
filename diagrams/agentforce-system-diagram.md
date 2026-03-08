# Agentforce Service Agent – System Diagram

## Overview

This diagram illustrates the architecture of the Agentforce Service Agent used for Coral Cloud Resorts. It shows how customer interactions flow through the AI agent, topics, actions, Salesforce flows, and CRM data.

---

# System Architecture Diagram

```mermaid
flowchart TD

A[Customer] --> B[Experience Cloud Chat]

B --> C[Agentforce Service Agent]

C --> D[Topic Selector]

D --> E[Experience Management Topic]

E --> F1[Get Customer Details Action]
E --> F2[Get Experience Details Action]
E --> F3[Get Sessions Action]
E --> F4[Create Experience Booking Action]

F1 --> G1[Customer Verification Flow]
F2 --> G2[Experience Retrieval Flow]
F3 --> G3[Session Retrieval Flow]
F4 --> G4[Booking Creation Flow]

G1 --> H1[(Contact Object)]
G2 --> H2[(Experience Object)]
G3 --> H3[(Session Object)]
G4 --> H4[(Experience Booking Object)]