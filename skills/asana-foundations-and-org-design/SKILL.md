---
name: asana-foundations-and-org-design
description: Start here when someone new to Asana wants to organize a business: teaches the basics, interviews them, and produces an Org Blueprint. Step 1 of 3.
---

# Asana Coach 1 of 3: Foundations and Org Blueprint

## The series
Three skills that work as one workflow. Each reads and updates the same **Asana Blueprint** document.

1. **asana-foundations-and-org-design** (this one): teach the basics, learn the business, design the structure, rank the workflows. Output: Blueprint sections 1 to 3.
2. **asana-workflow-automation-design**: turn one workflow into a Workflow Spec (stages, fields, form, rules, dashboard, edge cases). Output: Blueprint section 4.
3. **asana-build-launch-optimize**: build, test, launch, train, then review and improve. Output: Blueprint sections 5 and 6. Then loop back to skill 2 for the next workflow.

Blueprint sections: 1 Org profile, 2 Structure map, 3 Workflow backlog (ranked), 4 Workflow specs, 5 Build log, 6 Launch and review log, 7 Decisions and open questions.
Make the Blueprint a shareable document (a Docs artifact if that type is available, otherwise a markdown file). If the session belongs to a project, save it there too so later sessions find it. A starting template is in `templates/asana-blueprint-template.md` of this repository.

## How to coach (applies to every step)
- Assume zero Asana knowledge. The first time a term comes up, explain it in one or two plain sentences plus an example from *their* business.
- Ask in rounds with AskUserQuestion (or plain numbered questions if that tool is missing): 1 to 4 multiple-choice questions, each with an "I'm not sure" option and a marked recommended option. Say in one line why you are asking.
- After every round, play back what you heard in 3 to 5 bullets and get a yes before moving on. Show something concrete (a table, a diagram) at least every second round.
- Recommend, don't just ask. Beginners need a default; tell them what you would do and why.
- Keep the Decisions list current. Never design around a feature without checking their plan has it.
- If an Asana connector is available, offer to read the workspace (teams, projects, portfolios) read-only to ground the conversation. Do not create or change anything in this skill without an explicit yes.

## Step 0: Where are they starting?
Round of questions:
- Asana experience: never used it / used tasks only / manage projects / workspace admin.
- Account and plan: no account yet / Personal or free / Starter / Advanced / Enterprise / don't know. (Forms, rules, portfolios, goals, approvals and dashboards differ by plan. Have them check Admin console > Billing, or asana.com/pricing.)
- Organization size: just me / 2-10 / 11-50 / 50+.
- Goal: organize my own work / fix one process / organize a team / design the whole organization.
Routing: if they already have a working structure and want one process fixed, do a short Step 2 and Step 4 and hand off to skill 2.

## Step 1: Asana in ten minutes (the mental model)
Teach this hierarchy with a table that uses their business for the examples:

| Level | What it is | Rule of thumb |
|---|---|---|
| Organization / workspace | Everyone at the company | One per company domain |
| Team | A group of people who work together | Follows people, not processes |
| Portfolio | A leader's window onto several projects | Group by department, client, or goal |
| Goal | A measurable outcome ("cut response time to 48h") | Few, owned, connected to projects |
| Project | A body of work | Either a time-bound effort or an ongoing process |
| Section | Groups tasks in a project | Stages for a process, phases for an effort |
| Task | One unit of work | One owner, one due date |
| Subtask | A step inside a task | Checklist items with their own owner |
| Custom field | Structured data on tasks | If you will ever count, filter or route on it, it is a field |

Also introduce: views (List, Board, Timeline, Calendar), Forms (intake), Rules (automations), Templates, Dashboards/Reporting, My Tasks, Inbox.

Five principles to state plainly:
1. Every task has exactly one owner and a due date. "Everyone" means no one.
2. Ongoing processes (requests, approvals, intake) are "process projects" that never end: work flows through sections. This is where most automation lives.
3. Data goes in fields, not in task names or descriptions.
4. One task can live in several projects (multi-homing) instead of being duplicated.
5. Start small. Five projects people use beat fifty nobody opens.

Offer a 5-minute hands-on exercise: create a project "ZZ Sandbox", add three tasks, a section, a single-select field, switch to Board view. Explain they can practise there without breaking anything.

## Step 2: Discovery interview
Ask for documents first: org chart, staff list, spreadsheets used to track work, existing forms, SOPs, strategic plan. Read every one before proposing anything.

Then run these rounds (adapt the options to what you already know):
- **A. The business:** what you deliver, to whom; departments or functions; who leads each; who has final say.
- **B. How work arrives and moves:** email / web form / meetings / phone or walk-in / another tool; where it is tracked today (spreadsheet, email, paper, nothing); who approves what (spending, content, hiring).
- **C. Pain:** what falls through the cracks; where things wait; what leadership asks for that is hard to produce; what repeats weekly, monthly, yearly.
- **D. Direction:** the 3 to 5 goals or KPIs for this year, and who owns each.

Best technique: "Walk me through the last time this happened, step by step." Real stories expose handoffs and waiting that abstract answers hide.

## Step 3: Design the structure
Guidelines:
- Teams: usually one per department plus one org-wide team for announcements and shared processes.
- Portfolios: one per leader's area of oversight (department, committee, client group or strategic goal).
- Goals: only if the plan supports them and leadership will review them; link projects or portfolios so progress rolls up.
- Projects: one per ongoing process, one per time-bound initiative. Not one per person, not one per month.
- Naming: "Dept - Name" for projects, "TEMPLATE - " for templates, "ZZ TEST - delete me" for tests.
- Access: members for staff who do the work, commenters for reviewers, guests for outside partners.

Anti-patterns to warn about: a project per person; tasks with no owner; status written in task names; data in descriptions; a giant "General" project; copying tasks between projects instead of multi-homing; more teams than departments.

Deliver a Structure map table (Team | Members and roles | Portfolio | Projects with type process/time-bound | Owner) and, where it helps, an inline diagram. Confirm it.

## Step 4: Workflow backlog
List every recurring process found in Step 2. Score each 1 to 3 on: how often it runs, how painful it is, how many people it touches, how easy it is. Recommend the first workflow: frequent, painful, moderately simple, with an owner who wants it fixed. An early win earns trust for the rest. Let the user pick.

## Step 5: Write the Blueprint and hand off
Write sections 1 to 3 and the Decisions list. Point out anything unverified (plan features, who approves). Optionally, if a connector can create teams or projects and the user says yes, create the empty structure now; otherwise give click-by-click steps.

Close with: "Next step: asana-workflow-automation-design for workflow #1, [name]."
