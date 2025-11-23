# Analysis Plan Template: Deep Dive into the Average Handle Time (AHT) of Advisers

## 1. Objective
What question are we answering?
- For instance, identify why AHT increased from 6.2 minutes to 7.4 minutes in the last 30 days and determine which call types or advisers contributed most.

## 2. Stakeholders
Who requested it and who will use the result?
- Requestor: Contact Centre Manager  
- Users: Team Leads, QA Team, etc.

## 3. Data Sources
List tables, files, systems, or endpoints.
- CRM Tools, Voice-to-text analytics software
- qa_results, survey_data, rw_call_data, agent_info

## 4. Transformations Needed
- Filters (e.g, inbound calls only)
- Joins (e.g, rw_call_data → agent_info on agent_id)
- Aggregations (e.g, Calculate AHT as talk_time + hold_time + wrap_time...Group by adviser, queue, call_type, and day)
- Logic assumptions (e.g, Remove test calls and training queues)

## 5. Metrics Involved
Define each metric clearly.
- AHT
- Calls handled
- % of Hold time
- Repeat caller rate
- QA compliance score

## 6. Edge Cases
What might break? What should I be aware of?
- Missing agent_id on some calls  
- Outliers above 30 minutes  
- Calls transferred between multiple queues  
PS: the above can be suggested by the stakeholder and yourself

## 7. Expected Output
Dashboard, table, email report, SQL result, etc.
- Executive summary (PDF or email)
- Breakdown dashboard in Power BI (Adviser Scorecard Dashboard)
- Table showing top 10 advisers driving AHT variance
- Recommended actions

## 8. Validation Steps
How will you confirm the result is correct?
- Compare output with telephony dashboard totals
- Cross-check adviser-level calls handled with WFM schedule
- Spot-check five random rows against raw data

## 9. Timeline
Expected delivery or stages.
- Week 1: Extract + initial cleaning  
- Week 2: Analysis + validation  
- Week 3: Dashboard + summary  
PS: Try to set realistic timelines
