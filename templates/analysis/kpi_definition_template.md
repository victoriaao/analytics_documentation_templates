# KPI Definition Template

## KPI Name: First Contact Resolution (FCR)

## Business Purpose
What decision does this KPI support?
- e.g, Measures how often customer issues are resolved in a single interaction without repeat calls. Helps evaluate service quality and agent effectiveness.

## Calculation
Exact formula.
- e.g FCR = (Number of customers who did not contact us again within 7 days) / (Total unique customers who contacted us)

## Data Sources
Tables, fields, and transformations.  
For example:
- rw_call_data (customer_id, call_datetime)
- customer_interactions (tickets, voice, chats, emails)
- agent_info

## Filters Included/Excluded
Be specific.  
For example:
- Exclude transfers between queues (treated as one interaction)
- Include inbound calls only
- Exclude calls with no valid customer_id

## Edge Cases
How nulls, zeros, or incomplete data are handled.  
For example:
- Customers who call back for a different issue
- Customers with merged accounts
- Channels (call + chat) counted separately

## Owner
Which team maintains this KPI?
- e.g, Contact Centre Analytics Team, Team leads

## Frequency
- e.g, Daily, weekly, monthly.
