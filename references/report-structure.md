# Training report — structure, depth and build order

Use the student's department template when they provide one. Everything below is the default.
Default length: about 7,500 words of body text (plus preliminary pages and appendices).
Scale the word budget up or down with the length of the placement, but keep the proportions.

## Preliminary pages

1. **Title page**: report title, student name, matric number, department, university, company,
   period, session. Use `[bracketed placeholders]` for anything the student did not give.
2. **Certification / attestation**: supervisor and coordinator signature blocks, left blank.
3. **Dedication** (optional) and **Acknowledgements** (~120 words, specific: supervisor by role,
   colleagues, family; no flattery lists).
4. **Abstract** (200–250 words): where, how long, what work streams, headline skills, one
   concrete result. Write it last.
5. **Table of contents**, **List of figures**, **List of tables**, **List of abbreviations**.

## Chapter 1 — Introduction (~700 words)

1.1 Background of SIWES: established by the Industrial Training Fund (ITF) in 1973; coordinated
    with the National Universities Commission (NUC) and other regulators; bridges classroom
    theory and workplace practice.
1.2 Objectives of SIWES: acquire industrial skills, learn real work methods and safety practice,
    ease the move from school to work, prepare for employment, strengthen employer involvement.
1.3 Objectives of my training at this company: 3–4 personal, specific objectives for this student.
1.4 Scope and duration: dates, weeks, days per week, department.

## Chapter 2 — Company profile (~900 words)

2.1 History and location
2.2 Vision/mission (only if known or verifiable)
2.3 Organisational structure — include an org-chart figure (Mermaid or hand-drawn)
2.4 Products and services
2.5 The department I was attached to, and how it fits the business
2.6 Workplace safety and conduct rules observed

**Company facts are never invented.** Founding year, address, headcount, clients and mission
must come from the student, from publicly verified sources, or be written as
`[Student to confirm: ...]`. Only day-to-day activities may be drafted by inference.

## Chapter 3 — Training experience (~3,000 words — the heart of the report)

3.1 Orientation and induction (week 1)
3.2 Work streams: group the weeks into 3–5 themes.
    For each theme write:
    - The task and why the business needed it
    - Tools and equipment used (named; include versions where relevant)
    - The procedure as numbered steps (the examiner's technical-content evidence)
    - The result and how it was verified
3.3 Case studies: 2–3 deep dives, ~350 words each.
    Structure: symptom → diagnosis (what was ruled out, in order) → fix → validation → lesson.
    Prefer real incidents from the student's chat or logbook.
3.4 Weekly summary table: Week | Dates | Focus | Key output
3.5 Tools and technologies table: tool | purpose | where used
3.6 Skills acquired: technical and professional (communication, ticketing, time management, safety)

Include at least **6 figures** across the report (org chart, workflow, network topology, block
diagram, student photos from the image folder) and **4 tables**. Number them by chapter
(Figure 3.2, Table 3.1), caption them, and refer to every one in the text.

Where only a photograph can show something, insert the student's image by filename with a
caption. If there is no photo, add `[Insert photo: ...]` — never generate a fake screenshot.

## Chapter 4 — Linkage to theory (~900 words)

4.1 Table: task | engineering concept | how the concept explained what I saw.
    Use course titles from theory-linkage-bank.md or the student's own list.
    Never print a course code the student did not give.
4.2 Two worked examples with the actual principle written out.
    See writing-style.md for the strong vs weak example.
4.3 What the classroom had not yet covered, and how that sets up future courses.

## Chapter 5 — Challenges, conclusions, recommendations (~900 words)

5.1 Challenges and how each was handled (table: challenge | cause | action | outcome)
5.2 Conclusion: 150–200 words that follow from Chapters 3–4, with no new facts.
5.3 Recommendations, grouped by audience, at least two each and each one actionable:
    - The company
    - The department / university
    - ITF / SIWES coordinators
    - Future SIWES students

## Back matter

- **References**: IEEE numeric by default; follow the department style if given. Cite only
  sources that exist (manufacturer datasheets, standards, textbooks, vendor documentation).
  If unsure a source exists, leave it out.
- **Appendices**: logbook excerpt, photo plates from the image folder, attendance/commendation
  if any.

## Build order

1. Evidence ledger → outline with word budgets.
2. Write Chapter 3 first (it holds the evidence), then Chapters 4, 2, 5, 1.
3. Write the abstract and acknowledgements last.
4. Assemble, number figures and tables, generate the lists, then run the QA checklist
   in SKILL.md.

## Output format

Produce the report as Markdown (.md) and offer to convert to .docx. Use standard heading
levels (# for chapter, ## for section), numbered figures and tables, and cite every figure
and table by number in the body text.
