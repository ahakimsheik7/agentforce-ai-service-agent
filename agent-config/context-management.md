# Context Management

## Overview

Context management allows the Agentforce Service Agent to remember important information during a conversation. This capability enables the agent to perform multi-step workflows without repeatedly asking the customer for the same information.

By maintaining conversation context, the agent can track details such as the customer's identity, the selected experience, and the session being discussed.

This allows the AI agent to provide a smooth and efficient customer experience.

---

## Purpose of Context Management

Context management enables the agent to:

• Remember important information during the conversation  
• Support multi-step workflows  
• Avoid asking customers for the same information repeatedly  
• Maintain continuity in the interaction  

Without context management, the agent would treat every message as a new request.

---

## Context Values

During the conversation, the agent stores important values returned by actions and flows.

Examples of stored values include:

Contact ID  
Experience ID  
Session ID  

These values are reused when additional actions are executed.

---

## Context Sources

Context values typically come from the outputs of agent actions.

Examples include:

Get Customer Details → returns Contact ID  
Get Experience Details → returns Experience ID  
Get Sessions → returns Session ID  

These values are stored in the conversation state so they can be reused later in the workflow.

---

## Example Conversation Workflow

Step 1  
Customer asks about an experience.

Example:

Tell me about the Underground Cave Exploration.

The agent retrieves experience details.

Stored context:

Experience ID

---

Step 2  
Customer asks to see available sessions.

The agent retrieves session information.

Stored context:

Session ID

---

Step 3  
Customer requests to book a session.

The agent uses the stored context values to create the booking.

Required values:

Contact ID  
Session ID  
Number of Guests

---

## Multi-Step Interaction Example

Customer message:

I want to book the cave exploration for tomorrow.

Agent reasoning:

1. Verify the customer using Get Customer Details  
2. Retrieve available sessions using Get Sessions  
3. Use the stored session information  
4. Execute Create Experience Session Booking

Because the agent stores context, it can complete the workflow without asking the customer to repeat information.

---

## Benefits of Context Management

Context management improves the customer experience by:

• Reducing repetitive questions  
• Enabling multi-step workflows  
• Maintaining continuity across messages  
• Supporting more natural conversations

It also allows the AI agent to operate more efficiently by reusing previously retrieved data.

---

## Security Considerations

Context data is handled within the security boundaries of Salesforce.

Security protections include:

• Controlled access to CRM records  
• Role-based permissions  
• Secure flow execution

Sensitive customer information is only accessed through authorized actions.

---

## Summary

Context management enables the Agentforce Service Agent to maintain conversation state and support complex workflows.

By storing key values such as Contact ID, Experience ID, and Session ID, the agent can execute multiple actions across a conversation without requiring the user to repeat information.

This capability is essential for creating intelligent AI agents that provide smooth and efficient customer service interactions.