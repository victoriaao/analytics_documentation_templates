# Logic Documentation

## Problem Statement 
Why does this logic exist?
- e.g Standardise call type categories across telephony, CRM tickets, and chat.

## Data Sources
Exact tables, schemas, or files used.
- rw_calls_data, crm_tickets, chat_logs etc.

## Logic Breakdown
Step-by-step explanation.
1. Map telephony call reasons using the reason_code lookup.
2. For CRM tickets, classify based on ticket_category and metadata.
3. Chat logs classified using keyword grouping (billing, delivery, cancellation).
4. Merge all channels on customer_id + 24-hour window.
5. Final call_type hierarchy:
   - Billing
   - Delivery
   - Complaint
   - Cancellation
   - Technical Support

## Business Rules
Rules applied based on stakeholder requirements.
- If a CRM ticket and call occur within 24 hours, CRM category overrides the telephony reason.
- Complaints take precedence over all other categories.

## Assumptions
What the logic assumes about the data.
- reason_code values have not changed in the last 90 days.

## Limitations
Known caveats or data issues.
- Does not support sentiment scoring yet.
- Manual categorisation not captured for legacy calls.

## Output Description
Where this model/metric is used.
Used in AHT, FCR, and staffing models.

## Change History
- 2025-01-12: Added chat classification
- 2025-03-02: Updated CRM mapping rules
