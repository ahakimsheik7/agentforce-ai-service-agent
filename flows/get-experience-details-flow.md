
## Logic

1. Receive email and membership number from the agent.
2. Query the Salesforce Contact object.
3. Match the record where:

Email = input email  
Membership_Number__c = input membership number

4. Return the matching Contact record.

## Output

Contact ID

The Contact ID is stored in the conversation context and used for future actions.

---

# 2. Get Experience Details Flow

## Purpose

The **Get Experience Details Flow** retrieves information about a resort experience requested by the customer.

Examples of experiences include:

Scuba Diving  
Kayaking  
Underground Cave Exploration  
Full Moon Beach Party

## Input

Experience Name

## Logic

1. Receive the experience name from the agent.
2. Query the Experience__c object.
3. Retrieve the corresponding experience record.

## Output

Experience ID  
Experience Description  
Experience Duration  
Experience Location

The agent summarizes the returned information for the customer.

---

# 3. Get Sessions Flow

## Purpose

The **Get Sessions Flow** retrieves available session times for a selected experience.

Customers must select a session before booking an activity.

## Inputs

Experience ID  
(Optional) Session Date

## Logic

1. Receive the Experience ID from the agent.
2. Query the Session__c object.
3. Retrieve sessions associated with the selected experience.
4. Filter sessions by date if provided.

## Output

Session ID  
Session Date  
Session Time

The agent presents these options to the customer.

---

# 4. Create Experience Session Booking Flow

## Purpose

The **Create Experience Session Booking Flow** creates a reservation record in Salesforce.

This flow completes the booking process.

## Inputs

Contact ID  
Session ID  
Number of Guests

## Logic

1. Receive booking information from the agent.
2. Create a new Experience_Booking__c record.
3. Associate the booking with the Contact and Session records.

## Output

Booking Record ID

This confirms that the reservation has been successfully created.

---

# Salesforce Objects Used

The flows interact with several Salesforce objects.

Contact  
Stores customer identity information.

Experience__c  
Stores resort activity information.

Session__c  
Stores available time slots for each experience.

Experience_Booking__c  
Stores customer reservations.

---

# Example End-to-End Workflow

Customer message:

"I want to book the Underground Cave Exploration for tomorrow."

Agent workflow:

1. Execute Get Customer Details  
2. Execute Get Experience Details  
3. Execute Get Sessions  
4. Execute Create Experience Session Booking  

The flows retrieve and process the data required to complete the customer's request.

---

# Security Considerations

These flows operate within Salesforce security boundaries.

Security protections include:

• Role-based permissions  
• Controlled access to CRM objects  
• Customer identity verification before booking  

These safeguards ensure that customer data is handled securely.

---

# Summary

The Customer Experience Booking Flow architecture enables the Agentforce Service Agent to handle resort activity inquiries and bookings.

By combining multiple Salesforce Flows, the AI agent can verify customers, retrieve experience information, check available sessions, and create reservations while maintaining secure and structured access to Salesforce CRM data.