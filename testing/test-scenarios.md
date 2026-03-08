# Agentforce Service Agent – Test Scenarios

## Overview

This document describes the test scenarios used to validate the behavior of the Agentforce Service Agent.

Testing ensures that the AI agent correctly identifies customer requests, executes the appropriate actions, and successfully completes booking workflows.

All tests were performed using the **Agentforce Builder Preview Mode** and the **Experience Cloud site messaging interface**.

---

# Test Scenario 1: Retrieve Experience Information

## Objective

Verify that the agent can retrieve information about a resort experience.

## User Input

Can you tell me about the Underground Cave Exploration?

## Expected Agent Behavior

1. Detect experience inquiry intent.
2. Select **Experience Management Topic**.
3. Execute **Get Experience Details** action.
4. Retrieve experience information from Salesforce.
5. Summarize the experience details for the customer.

## Expected Result

The agent returns a description of the experience including:

Experience description  
Location  
Duration

---

# Test Scenario 2: Customer Verification

## Objective

Verify that the agent requests and validates customer identity before performing booking actions.

## User Input

I want to book the cave exploration experience.

## Expected Agent Behavior

1. Detect booking intent.
2. Request verification information from the customer.

Example request:

Please provide your email address and membership number.

## User Response

Email: sofiarodriguez@example.com  
Membership Number: 10008155

## Expected Result

The agent executes the **Get Customer Details** action and retrieves the Contact record.

---

# Test Scenario 3: Retrieve Available Sessions

## Objective

Verify that the agent retrieves available sessions for an experience.

## User Input

Show me available sessions for tomorrow.

## Expected Agent Behavior

1. Execute **Get Sessions** action.
2. Retrieve session records associated with the experience.

## Expected Result

The agent presents available sessions such as:

10:00 AM  
2:00 PM  
6:00 PM

---

# Test Scenario 4: Create Booking

## Objective

Verify that the agent can successfully create a booking.

## User Input

Book the 2 PM session for 2 guests.

## Expected Agent Behavior

1. Execute **Create Experience Session Booking** action.
2. Create a booking record in Salesforce.

## Expected Result

A new **Experience_Booking__c** record is created.

The agent confirms the booking.

Example response:

Your reservation has been successfully booked.

---

# Test Scenario 5: Invalid Customer Verification

## Objective

Ensure the agent properly handles invalid customer information.

## User Input

Email: fake@example.com  
Membership Number: 000000

## Expected Agent Behavior

The **Get Customer Details** flow returns no matching Contact record.

## Expected Result

The agent informs the customer that verification failed and requests correct information.

Example response:

We could not verify your membership details. Please check your email and membership number.

---

# Summary

Testing confirms that the Agentforce Service Agent correctly performs the following operations:

• Experience information retrieval  
• Customer identity verification  
• Session retrieval  
• Booking creation  
• Error handling for invalid inputs

These test scenarios validate the reliability and functionality of the AI agent within the Salesforce environment.