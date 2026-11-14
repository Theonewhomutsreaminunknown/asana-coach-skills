# Asana best practices

A practical reference used by the Asana Coach skills. Feature availability and limits depend on your Asana plan and change over time, so check before relying on any one of them.

## 1. Structure
- **Teams follow people.** Create teams around groups who work together and need to see the same things, usually one per department plus one org-wide team.
- **Portfolios are for leaders.** Group the projects a leader oversees (by department, committee, client or strategic goal) so status can be seen in one place.
- **Goals are few and measurable.** Three to five per level, each with an owner and a number, linked to the projects or portfolios that move it.
- **Two kinds of project.** *Process projects* never end (requests, approvals, intake); work flows through sections. *Time-bound projects* have an end date (a launch, an event, a renovation). Know which one you're building.
- **Start small.** Build the minimum structure that supports the first workflows; add more only when it's used.

### Anti-patterns
| Avoid | Do instead |
|---|---|
| A project per person | Use My Tasks and assignees |
| A project per month or year | One process project, filter by date |
| Status in task names ("APPROVED - Vendor X") | A status field or section |
| Data in descriptions | Custom fields |
| Copying a task into another project | Multi-home the same task |
| Tasks with no owner or due date | One owner, one date, always |
| A giant "General" project | Specific projects with clear purpose |

## 2. Naming and conventions
- Projects: `Dept - Name` (e.g. `Finance - Purchase Requests`).
- Templates: `TEMPLATE - Name`.
- Tests: `ZZ TEST - delete me` so they sort last and are easy to find and remove.
- Fields: plain names a stranger would understand; options short and mutually exclusive.
- Write each project's purpose, owner and "how requests get here" in the project overview.

## 3. Designing a workflow
- **Map the real process first.** Walk through the last real instance step by step; draw a swimlane per role.
- **Improve before automating.** Remove steps that add no value; question approvals that exist by habit, not policy.
- **One item = one task.** The request or case is the task; stages are sections.
- **Fields for anything you'll count, filter or route on.** Single-select for routing, number for amounts, date, people.
- **Forms for intake.** Map every answer to a field; use branching for category-specific questions; make every question that a rule depends on required.
- **End states matter.** Include Done, Rejected, Cancelled and Needs more info sections.

## 4. Automations (rules)
Anatomy: **Trigger** → optional **Check if** → **Actions**.

### Proven patterns
1. Intake triage (form submitted → section, assignee, status)
2. Route by field (category/department → assignee)
3. Tiered approvals (amount → approval track; approve → next stage; reject → Rejected; needs info → back to requester)
4. Fan-out (one request creates tasks in other teams' projects with relative due dates)
5. Date change (create a "re-date" task; rules don't move what they already created)
6. Time-based (reminders before; overdue → escalate or close)
7. Cancel (close-out task + move)
8. Close-out (Done → complete + notify requester)

### Limits we hit in practice (verify on your plan)
- Rules have a step cap (about 15 including the trigger). Split long rules.
- A Paths step runs only the first matching branch, so multi-select options usually need one rule each.
- Rules can also fire on subtasks.
- Relative dates are computed from the task's due date, not from date custom fields.
- Rules can't set dependencies or copy attachments.
- Tasks created by the repeating-task feature may not trigger "task added" rules.
- Moving a task can reset an approval status.
- Some report filters can't express "is empty" or "no assignee"; label workaround charts clearly.
- Copying a rule can carry over the source project into "create task" steps; check every step after copying.
- The rule builder has no drafts; finish a rule in one sitting.

### Edge cases to design for
Blank fields · short-notice dates (generated tasks land in the past) · changed dates · cancellations · duplicates · rejections · send-back loops · absent approvers · submitters without an Asana account.

## 5. Building safely
- Build in order: project → sections → fields → form → templates → rules → dashboard → members and assignees.
- Keep real assignees off until launch; assigning people notifies them.
- Use `ZZ TEST - delete me` names and far-future dates for tests.
- Archive instead of delete; archiving is reversible.
- Keep a build log with links/IDs and every deviation from the spec.

## 6. Testing
- One test per branch, plus every edge case.
- Confirm each rule fires exactly once, and nothing lands in the wrong project.
- Test with a non-admin submitter.
- Get the owner's go-ahead before any test that notifies real people.
- After a fix, re-run the failing test and every test touching the same rule.

## 7. Launch and adoption
- Put the form link where requests already start (website, email signature, chat, intranet).
- Announce a cutoff date for the old process; archive the old project.
- Give each role a one-page guide: what do I do differently from Monday?
- Run old and new in parallel briefly for risky processes.
- Leaders model the behaviour: comment and approve in Asana, not by email.

## 8. Reporting
- Start from leadership's questions, then map one chart to each.
- Typical set: items by stage, overdue, by owner, totals by category or department, cycle time.
- Fewer, clearer charts; dashboards have widget limits.

## 9. Continuous improvement
- Review at 2 weeks, then 30, 60, 90 days.
- Look for: form usage vs email, bottleneck sections, overdue rate, cycle time, rule misfires, manual workarounds.
- Ask each role: what's easier, what's annoying, what's missing.
- Change one thing at a time, update the spec, re-test affected rules.
- Every 3 to 5 workflows, revisit the org structure, cross-team handoffs, portfolios and goals.
