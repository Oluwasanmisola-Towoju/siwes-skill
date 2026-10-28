# Logbook generation rules

Run only when the student answered yes to the logbook question and gave start and end dates.
The logbook earns 30 marks: weeks covered, illustrations, neatness, technical content, relevance.

## 1. Build the calendar first

Lay out every working day from start date to end date.
- One entry per working day. The number of entries per week equals the days the student worked.
- If the student gave only a count and not specific days, use Monday–Friday as the default
  and note the assumption in the review sheet.
- Week 1 is the Monday-to-Sunday week containing the start date. A mid-week start gives a
  short Week 1; say so.

## 2. Decide what is real and what is drafted

For every working day, label the source in the evidence ledger:
- **R (real)**: the student's logbook or chat names the task and (directly or by context) the day.
- **D (drafted)**: no evidence for that day. Draft from the student's field profile.

Anchoring real events to dates:
1. Use explicit dates first.
2. Then relative hints ("yesterday", "this morning", "after the lightning strike").
3. Otherwise keep real events in the order told and spread them across the calendar
   in proportion to where they fall in the chat.
4. Never put an event on a non-working day, or invent a date the evidence contradicts.

If real evidence is thin (fewer than ~8 distinct activities), build the whole placement from
the field profile. State the assumptions in the review sheet. Do not stall to ask for more.

## 3. The placement arc (for drafted days)

Make the weeks feel like a real placement, not 40 copies of the same day:

- **Weeks 1–2**: induction, safety, tour of departments, shadowing, learning tools, small
  supervised tasks.
- **Middle weeks**: increasing independence. Repeat task types with a different fault,
  location or tool each time, escalating autonomy: "assisted" → "performed under supervision"
  → "carried out independently."
- **Later weeks**: a small project or improvement (documentation, a deployment, a layout plan,
  a test script), then handover and review.
- Include unglamorous days: inventory, documentation, waiting for a part, a team meeting,
  a retraining session. Real placements have them.
- No more than two consecutive days of the same category (hardware / software / networking / admin).
- At most one major incident per three weeks.

## 4. Anatomy of one entry (45–90 words)

Action or problem → tools, commands or components → result and how it was checked.

- Start each entry with a different verb. Past tense, first person implied.
  ("Diagnosed...", "Re-crimped...", "Installed...", "Verified...", "Configured...")
- Name the specific thing: the port, the component, the command, the fault symptom.
- End with validation: what was tested and what the outcome was.
- Remarks column: the Computer Engineering concept or principle the day connects to.

**Upgrade informal notes into logbook-grade language while keeping every fact the student gave:**

| Informal | Logbook-grade |
|---|---|
| "Fixed the internet" | "Traced the loss of connectivity to a failed gateway, switched the branch to the backup router, and confirmed routing with ping and tracert across the subnet." |
| "Soldered a touch screen" | "Re-flowed the connections on the touch-controller IC of a POS display with a hot-air station and checked touch calibration under the live interface." |
| "Checked a laptop" | "Ran hardware diagnostics, reviewed BIOS device settings, and cleared a locked USB root hub state in Device Manager before retesting peripherals." |
| "Helped with the network" | "Assisted the network engineer in documenting the switch port allocations for the new office wing, using the switch admin panel to confirm VLANs and recording each port's assignment in the inventory sheet." |

## 5. What must never be invented, even in drafted days

- Names of real people (use roles: "my supervisor", "a senior technician").
- Serial numbers, IP addresses, SSIDs, costs, downtime figures or percentages.
- Claims that need paperwork (certificates earned, formal commendations, incident report numbers).
- Anything the student's evidence contradicts.

Drafted days stay generic enough to be plausible for any business of that type.

## 6. Illustrations (5 marks)

- At least one numbered Figure per week.
- Choose a diagram that matches that week's work: LAN topology, flowchart, block diagram,
  circuit schematic, process diagram, simple bar chart.
- When the facts support it, render the diagram (Mermaid or matplotlib code block) and embed it.
  Otherwise write a specific sketch description so the student can draw it themselves.
- If a real photo from the student's evidence matches the week, cite the filename.

Format: `**Figure N.M:** [specific description of what the diagram shows]`

## 7. Layout (every week uses the same format)

```markdown
## Week N (DD Mon – DD Mon YYYY)
| Day | Date | Unit / Location | Work done | Tools / equipment | Skills & remarks |
|---|---|---|---|---|---|
| Mon | DD-Mon-YYYY | ... | ... | ... | ... |
| Tue | DD-Mon-YYYY | ... | ... | ... | ... |

**Weekly summary:** two sentences on what the week achieved overall.
**Figure N.1:** [specific description of the illustration for this week]
**Supervisor's comment:** ______________________ **Signature / Date:** ______________
```

Rules:
- Dates always `DD-Mon-YYYY` (e.g., 14-Sep-2026).
- Do not change the column order.
- The student can request a spreadsheet or Word version of the same table.

## 8. Header block (once at the top of the logbook)

```markdown
# SIWES Logbook: [Company Name], [Start Date] – [End Date]

**Student:** [Full Name] | **Matric:** [No.] | **Department:** Computer Engineering
**University:** [Name] | **Supervisor:** [Role / Name if given]
```
