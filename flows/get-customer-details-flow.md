# Customer Experience Booking Flow Architecture

## Overview

This document describes the Salesforce Flow architecture used by the Agentforce Service Agent to support resort activity inquiries and bookings.

These flows allow the AI agent to verify customers, retrieve experience information, check available sessions, and create bookings.

Each flow acts as an automation component that connects the Agentforce AI agent to Salesforce CRM data.

---

# Flow Workflow

The booking process follows a structured sequence of flows.

Customer Request  
↓  
Customer Verification  
↓  
Retrieve Experience Details  
↓  
Retrieve Available Sessions  
↓  
Create Booking

Each step is handled by a Salesforce Flow triggered by an Agentforce action.

---

# 1. Get Customer Details Flow

## Purpose

The **Get Customer Details Flow** verifies the identity of the customer interacting with the agent.

This verification ensures that bookings and other operations are linked to the correct Salesforce Contact record.

## Inputs

Email  
Membership Number

Example:
