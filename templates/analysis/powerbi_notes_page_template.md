# Power BI Notes Template

## Dataset Used  
For example:
- Table Name: Telephony_Agent_Performance
- Imported from: SQL Server → cc_dwh.telephony_agent_daily
- Refresh: Daily at 06:00 AM
- Filters applied at model level:
  - Only inbound calls
  - Excludes test numbers and internal extensions

## Measure Definitions
List DAX formulas used.
For example:
- AHT (Average Handle Time)
AHT = DIVIDE([Total_Handle_Time], [Calls_Handled])  
  where:
  - Total_Handle_Time = SUM(Calls[Talk_Time] + Calls[Hold_Time] + Calls[Wrap_Time])  
  - Calls_Handled = DISTINCTCOUNT(Calls[Call_ID])
  
## Key Assumptions
- Each Call_ID represents a unique customer interaction.
- A wrap time of 0 is treated as valid, not missing.
- CSAT surveys are assumed to be linked correctly to the latest call per customer within 24 hours.
- Only production queues are included (no training or test queues).

## Filters and Their Behavior
- Date Slicer filters all visuals based on Calls[Call_Date].
- Queue Filter changes AHT, CSAT, and FCR to reflect only selected queues.
- Advisor Filter limits visuals to calls handled by selected advisers but does not change overall call volume cards unless “Single Adviser View” is toggled on.
- Channel Filter (Voice, Chat, Email) affects KPIs that are channel-aware. AHT is calculated per channel basis when multiple channels are selected.

## Limitations and Known Issues
- CSAT responses are optional; results may be biased toward customers who chose to respond.
- FCR does not yet factor in cross-channel repeats (e.g., call → email).

## Last Updated Date
- Notes last updated: 07 March 2025
- Updated by: name / Analytics Team
