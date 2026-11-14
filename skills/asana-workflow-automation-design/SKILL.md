---
name: asana-workflow-automation-design
description: Use to turn one business process into an Asana Workflow Spec: stages, fields, form, rules and dashboard, with guided questions for beginners. Step 2 of 3.
---

# Asana Coach 2 of 3: Workflow and Automation Design

Part of a series: asana-foundations-and-org-design, then this skill, then asana-build-launch-optimize. All three share the **Asana Blueprint** doc.

## Inputs
- Read the Blueprint (structure, backlog, decisions, plan level). If there is none, run a 3-question mini-discovery (what the business does, which process, which Asana plan) and suggest skill 1 afterwards.
- Ask for any spreadsheet, form, email thread or SOP that shows the process today. Read it first.

Coaching style is the same as skill 1: multiple-choice rounds of 1 to 4 questions with a recommended option and "not sure", explain each new term once, play back after every round, show a diagram or table often.

## Step 1: Map the process as it is today
Questions to cover (spread across rounds):
- **Trigger:** what starts it? (a request, a date, a calendar cycle, an email)
- **Intake:** who asks, and what information is needed to start work?
- **Stages:** what happens, in order? Who acts at each stage?
- **Decisions:** where does it branch? (approve/reject, amount thresholds, category, department)
- **Handoffs:** which steps belong to another team?
- **Done:** what does finished mean, and who needs to know?
- **Exceptions:** cancellations, date changes, send-backs for missing info, rush requests, duplicates.
- **Volume and timing:** how many per month, deadlines, service levels.

Walk through the last real instance step by step. Then draw the current flow as an inline swimlane diagram (one lane per role) and confirm it.

## Step 2: Improve before you automate
Automating a bad process just makes bad results faster. Ask:
- Which steps add no value or exist only out of habit?
- Where does work wait, and why?
- Which approvals are required by policy, and which by habit?
- What could happen in parallel instead of in sequence?
Agree the future flow and redraw it.

## Step 3: Translate into Asana objects

| In the process | In Asana |
|---|---|
| A request or intake | Form (answers map to fields; branching questions) |
| The item moving through | One task |
| A stage | A section (Board view shows the pipeline) |
| Data you route, filter or report on | Custom field: single-select for routing, number for amounts, date, people |
| A checklist for every item | Subtasks or a task template |
| Work on a schedule | Recurring task or project template |
| An approval | Approval task, an approval-status field, or a section move |
| Work handed to another team | A task created in that team's project, or the same task multi-homed |

Field design tips: prefer single-select over text for anything a rule depends on; keep option lists short and clearly worded; make every form question that a rule depends on **required** (a blank field means the rule never fires); name fields so a stranger understands them.

Define sections (stages) plus the end states: Done, Rejected, Cancelled, Needs more info.

## Step 4: Design the automations
Explain the anatomy: **Trigger** (when) then optional **Check if** (conditions or Paths) then **Actions** (do).
Common triggers: task added, form submitted, field changed, moved to section, due date approaching, overdue, completed, assignee changed.
Common actions: move to section, set field, assign, add collaborator, create task or subtask, add to another project, comment, set due date, mark complete, notify via an integration (plan dependent).

Pattern library (offer the ones that fit):
1. **Intake triage:** form submitted, move to Submitted, assign the triager, set status.
2. **Route by field:** check category or department, assign the right person.
3. **Tiered approvals:** amount sets an approval track; approve moves to the next stage; reject moves to Rejected and completes; "needs info" reassigns to the requester; resubmit returns to the stage.
4. **Fan-out:** one request creates tasks for other teams, due dates relative to the request's due date (for example a flyer 14 days before an event).
5. **Date change:** due date changed creates a "re-date" task, because rules do not move tasks they already created.
6. **Time-based:** reminder N days before; overdue by 1 day moves to Completed or Escalate.
7. **Cancel:** status Cancelled creates a close-out task and moves the item.
8. **Close-out:** moved to Done marks complete and tells the requester.

Write a numbered rules table: # | Rule name | Trigger | Conditions | Actions | Why.

Limits to verify before promising (they change; test in a scratch project when unsure):
- Rules have a step cap (about 15 steps including the trigger); split long rules.
- A Paths step runs only the first matching branch, so a multi-select with several options usually needs one rule per option.
- Rules may fire on subtasks too.
- Relative dates work from the task's due date, not from date custom fields.
- Rules cannot set dependencies or copy attachments.
- Copies made by repeating tasks may not trigger "task added" rules.
- Moving a task can reset an approval status.
- Report filters may not express "is empty" or "no assignee".
- Rules, forms and branching depend on the plan.

Edge-case checklist: blank fields, short-notice dates (generated tasks dated in the past), changed dates, cancellations, duplicates, rejections, send-back loops, absent approvers, submitters without an Asana account.

## Step 5: Reporting
Ask which questions leadership needs answered (How many are waiting at each stage? What is overdue? Totals by department? Who is overloaded?). Map each to one dashboard chart. Fewer, clearer charts.

## Step 6: Write the Workflow Spec
Add to Blueprint section 4 (or a separate doc linked from it; template in `templates/workflow-spec-template.md`):
1. Purpose and success measure (for example "approval in under 5 days")
2. Roles: requester, doer, approver, informed
3. Current and future flow diagrams
4. Project setup: sections, views, custom fields with every option
5. Form: each question, the field it maps to, required or not
6. Rules table
7. Dashboard charts
8. Edge cases and how each is handled
9. Known limits and workarounds
10. Open questions and decisions
11. Test plan seed: one test per branch and edge case

Ask who else must review it (process owner, approvers) before building. Close with: "Next step: asana-build-launch-optimize."
