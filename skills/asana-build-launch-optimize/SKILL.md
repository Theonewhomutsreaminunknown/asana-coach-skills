---
name: asana-build-launch-optimize
description: Use to build an approved Asana Workflow Spec, test it safely, launch and train the team, then review and improve it at 2, 30, 60 and 90 days. Step 3 of 3.
---

# Asana Coach 3 of 3: Build, Launch, Optimize

Part of a series: asana-foundations-and-org-design, asana-workflow-automation-design, then this skill. All three share the **Asana Blueprint** doc.

## Inputs
An approved Workflow Spec in the Blueprint. Do not build without one; if it is missing, offer a quick pass through skill 2 first. Building from a vague idea produces rules nobody can explain later.

## Step 1: Pick the build mode
Ask:
- **Coach mode (best for learning):** click-by-click instructions; the user builds, shares screenshots, Claude checks each piece.
- **Assisted mode:** Claude creates what the Asana connector supports (projects, tasks, some fields) and builds rules, forms and dashboards in the browser if browser tools are available, or falls back to coach mode for those pieces.
- **Mixed:** Claude builds, the user builds one rule themselves to learn how.

## Step 2: Build in dependency order
1. Project, sections, default view.
2. Custom fields, added to the project with every option from the spec.
3. Form: each question mapped to its field; required flags; share link not yet published.
4. Templates and standard subtasks.
5. Rules, in spec order, simplest first. Finish each rule in one sitting (the rule builder has no drafts). After copying a rule, check every step's project setting; copies can carry over the source project.
6. Dashboard charts.
7. Members, permissions and real assignees **last**, because they trigger notifications.

Safety rules:
- Until launch, leave rule assignees blank or set to the builder.
- Name test items "ZZ TEST - delete me" and date them far in the future.
- Never delete permanently. Archive replaced projects (reversible) and give the owner a search term to clear test items.
- Log every built object with its link or ID, every deviation from the spec, and why, in Blueprint section 5.

## Step 3: Test
Turn the spec's test seed into a table: Test | Steps | Expected | Actual | Pass / Fix.
Cover: the main path for every branch; each rule fires exactly once; blank fields; changed dates; cancel; reject; send back and resubmit; short notice; a submitter who is not an admin; nothing landing in the wrong project. Only test anything that notifies real people with their owner's go-ahead. Fix, then re-run the test that failed and any test touching the same rule.

## Step 4: Launch
Go-live checklist:
- Real assignees set in rules; members added with the right access.
- Form link placed where requests start (website, email signature, chat channel, intranet).
- Old process retired on an announced date; old project archived.
- Open decisions closed (required fields, short-notice handling, owners).
- For a risky process, run old and new in parallel for a short, fixed period.

Training: write a one-page quick guide per role (requester, doer, approver, leader) that answers "what do I do differently from Monday?" Suggest a 15-minute walkthrough using a real example.

## Step 5: Review and optimize
Checkpoints: 2 weeks, then 30, 60 and 90 days.
Look at (pull data through the connector and compute in code when available; otherwise use the dashboard):
- Are requests arriving through the form, or still by email?
- Where do tasks pile up (stage counts, time in stage)?
- Overdue rate and cycle time from submission to done.
- Rules misfiring or people working around them.
- What still happens outside Asana.
Ask 3 short questions of each role: what's easier, what's annoying, what's missing.

Turn findings into a short improvement list. Change one thing at a time, update the spec, log it in section 6, and re-test the affected rules.

Maturity ladder to show the user where they are:
1. Tasks with owners and dates.
2. Process projects with forms.
3. Automated routing and approvals.
4. Portfolios and dashboards leaders actually read.
5. Goals linked to work, reviewed on a regular rhythm.

## Step 6: Loop
Mark the workflow Launched in the backlog. Recommend the next one and hand back to asana-workflow-automation-design. After every 3 to 5 workflows, revisit the structure (skill 1, Step 3): cross-team handoffs, portfolios, goals, an organization-wide dashboard, and a regular review rhythm with leadership.
