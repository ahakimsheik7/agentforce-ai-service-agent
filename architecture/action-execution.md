# Action Execution

## Overview

Action execution is the stage in the reasoning architecture where the Agentforce Service Agent performs operations inside Salesforce. Actions allow the AI agent to retrieve information, validate customers, and perform business operations such as booking resort experiences.

Each action is connected to a Salesforce Flow, which performs the actual data retrieval or record creation.

Actions act as the bridge between the AI agent and Salesforce CRM data.

---

## Purpose of Actions

Actions allow the agent to interact with backend systems and perform tasks beyond simple conversation.

Actions enable the agent to:

• Retrieve data from Salesforce  
• Validate customer identity  
• Retrieve available experience sessions  
• Create booking records  

Without actions, the AI agent would only be able to generate responses but would not be able to perform real operations.

---

## Action Execution Process

When a customer request requires data or an operation, the agent executes an action.

The execution process follows this sequence:

Customer Request  
↓  
Topic Selection  
↓  
Instruction Evaluation  
↓  
Action Selection  
↓  
Flow Execution  
↓  
Data Returned to Agent  
↓  
Response Generation

This ensures that actions are only executed when the instructions in the topic require them.

---

## Actions Implemented

The Agentforce Service Agent uses several actions to manage resort experiences.

### Get Customer Details

Purpose:

Validate the identity of the customer using their email address and membership number.

Inputs:

Email  
Membership Number

Output:

Contact record from Salesforce.

This action ensures that bookings are linked to the correct customer.

---

### Get Experience Details

Purpose:

Retrieve information about a resort experience.

Example experiences include:

Scuba Diving  
Kayaking  
Underground Cave Exploration

The action retrieves the Experience__c record from Salesforce.

Returned data may include:

• Experience name  
• Description  
• Duration  
• Location

---

### Get Sessions

Purpose:

Retrieve available session times for a selected experience.

Example:

Experience: Underground Cave Exploration

Available sessions:

Tomorrow – 10:00 AM  
Tomorrow – 2:00 PM

The action retrieves Session__c records associated with the experience.

---

### Create Experience Session Booking

Purpose:

Create a booking record for a selected session.

Inputs required:

Contact__c  
Session__c  
Number_of_Guests__c

Output:

A new Experience_Booking__c record created in Salesforce.

This action completes the booking workflow.

---

## Example Action Execution

Customer message:

Tell me about the Full Moon Beach Party.

Agent reasoning:

Intent detected → Experience Inquiry

Topic selected → Experience Management

Instruction evaluated → Run Get Experience Details

Action executed → Get Experience Details

The flow retrieves the experience information and returns it to the agent.

The agent then generates a response for the customer.

---

## Multi-Step Action Execution

Actions can also be executed in sequence to complete more complex workflows.

Example booking workflow:

Step 1  
Get Customer Details

Step 2  
Get Experience Details

Step 3  
Get Sessions

Step 4  
Create Experience Session Booking

Each step retrieves information or performs an operation required to complete the customer's request.

---

## Security Considerations

Action execution operates within Salesforce security boundaries.

Security controls include:

• Role-based permissions  
• Controlled access to CRM data  
• Identity verification before booking actions  

These controls ensure that customer data is accessed securely.

---

## Benefits of Action-Based Architecture

Using actions provides several advantages:

• Secure access to Salesforce data  
• Structured automation workflows  
• Clear separation between AI reasoning and business operations  
• Scalable system design

New actions can be added as the agent expands to support additional services.

---

## Summary

Action execution allows the Agentforce Service Agent to perform real operations within Salesforce.

Actions connect AI reasoning with Salesforce Flow automation and CRM data.

This architecture enables the agent to retrieve information, validate customers, and automate booking workflows while maintaining secure and structured interactions.