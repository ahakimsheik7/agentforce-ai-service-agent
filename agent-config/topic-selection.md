# Topic Selection

## Overview

Topic selection is the process used by the Agentforce Service Agent to determine which topic should handle a customer request.

Topics organize the reasoning logic of the agent. Each topic contains instructions and actions that define how the agent should respond to a specific category of requests.

By grouping related logic inside topics, the agent can handle different types of conversations in a structured and scalable way.

---

## Purpose of Topics

Topics allow the agent to:

• Organize conversation logic  
• Handle different types of customer requests  
• Connect instructions with actions  
• Maintain predictable agent behavior  

Topics act as the main decision layer that determines how the agent processes user messages.

---

## Topic Selection Process

After the AI model detects the customer's intent, the agent selects the most appropriate topic to handle the request.

The process follows these steps:

Customer Message  
↓  
Intent Detection  
↓  
Topic Evaluation  
↓  
Topic Selection  
↓  
Instruction Execution

The selected topic then determines which instructions and actions should be used.

---

## Experience Management Topic

This project implements a primary topic called:

Experience Management

The Experience Management topic is responsible for handling customer interactions related to resort activities and bookings.

This topic supports several types of requests including:

• Learning about available experiences  
• Checking available session times  
• Booking experience sessions  
• Answering questions about activities

---

## Example Topic Selection

Customer message:
