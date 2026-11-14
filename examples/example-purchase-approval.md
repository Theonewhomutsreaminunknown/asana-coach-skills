# Worked example: Purchase approval workflow

A fictional small organization (25 staff, Asana Starter plan) used the series to replace email-based purchase approvals. This shows what each skill produced.

## Skill 1 output (excerpt)
**Backlog ranking**

| Workflow | Freq | Pain | People | Ease | Total |
|---|---|---|---|---|---|
| Purchase approvals | 3 | 3 | 3 | 2 | **11** |
| Event requests | 2 | 3 | 3 | 2 | 10 |
| Onboarding | 1 | 2 | 2 | 3 | 8 |

Picked: purchase approvals (weekly, lots of lost emails, finance lead keen to fix it).

## Skill 2 output (excerpt)
**Improve step:** approvals under $500 previously needed two signatures by habit; policy only required the department head. Removed one step.

**Sections:** Submitted · Dept Approval · Finance Review · Director Approval · Approved - Pay · Paid · Needs More Info · Rejected

**Fields**

| Field | Type | Options |
|---|---|---|
| Department | single-select | Operations, Programs, Marketing |
| Amount | number | |
| Approval Track | single-select | Up to $500, $501-$5,000, Over $5,000 |
| Vendor | text | |

**Form:** Request title, Department (required), Amount (required), Vendor, Purpose, Quote/Invoice attachment.

**Rules**

| # | Name | Trigger | Conditions | Actions |
|---|---|---|---|---|
| 1 | Set track | Amount changed | Amount ≤ 500 / 501-5,000 / > 5,000 | Set Approval Track |
| 2 | Route to dept head | Task added | Department = X | Move to Dept Approval, assign dept head |
| 3 | Dept approved | Approval = Approved in Dept Approval | Track = Up to $500 | Move to Approved - Pay, assign finance |
| 3b | Dept approved | same | Track ≠ Up to $500 | Move to Finance Review, assign finance |
| 4 | Finance approved | Approved in Finance Review | Track = Over $5,000 | Move to Director Approval |
| 5 | Reject | Approval = Rejected | - | Move to Rejected, comment, mark complete |
| 6 | Needs info | Approval = Changes requested | - | Move to Needs More Info, assign requester |
| 7 | Paid | Moved to Paid | - | Mark complete |
| 8 | Reminder | Due in 2 days | Not in Paid/Rejected | Comment to assignee |

**Edge cases:** blank amount → rule 1 clears track and nothing routes, so Amount is required on the form; resubmit from Needs More Info → requester moves it back to Submitted, which re-runs rule 2.

## Skill 3 output (excerpt)
**Tests:** one per track, a reject, a send-back and resubmit, a blank amount, a non-admin submitter. Two fixes: rule 3 originally lacked the track condition; rule copies had carried the wrong project into a step.

**Launch:** form link added to the intranet and finance's email signature; email approvals stopped on the 1st of the month; one-page guides for requesters, department heads and finance.

**30-day review:** 92% of requests came through the form; Finance Review was the bottleneck (avg 4 days). Change: a 2-day reminder for Finance Review only. **60-day:** average approval time down from 9 to 4 days.
