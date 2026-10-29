# Training Report — Format Reference

This file is loaded by the siwes-200l-comp-eng skill when writing the Training Report.
Use it alongside the writing rules in SKILL.md.

---

## TITLE PAGE — exact layout

```
[UNIVERSITY NAME]
DEPARTMENT OF COMPUTER ENGINEERING
(or ELECTRICAL AND ELECTRONICS ENGINEERING — use what the student gave)

STUDENT INDUSTRIAL WORK EXPERIENCE SCHEME (SIWES)
TRAINING REPORT

Name:           [Student Full Name]
Matric Number:  [XXX/XXXXXXXX]
Level:          [200L]
Session:        [e.g., 2025/2026]

Establishment:  [Company Name]
Period:         [Start Date] – [End Date]
Supervisor:     [Name or role, if provided; omit this line if not given]

Submitted in partial fulfilment of the requirements of the Industrial Training Programme
[Month, Year]
```

Do not invent founding year, headcount, revenue, or financial data. If not given, omit.

---

## CHAPTER 1 — Sample sentences by sub-section

### 1.1 Background to the Establishment
> "[Company Name] is a [industry descriptor] company based in [city, country]. The organisation [core mission]. It serves [target customers] and has built its offering around [key differentiator]."

Keep to one paragraph. Do not pad with generic industry description. Every sentence should be about this specific company.

### 1.2 Organisational Structure
> "The company operates a [lean / hierarchical / cross-functional] structure. Engineering is led by the [CTO / Head of Engineering] and divided into [teams if known]. I was embedded in the [team name] team and reported to [supervisor role]."

If unknown, write: "a cross-functional engineering team whose structure I became familiar with through daily stand-ups and project reviews."

### 1.3 Nature of Business
One to two paragraphs. What do they do, for whom, at what scale? Use only what the student gave plus publicly verifiable information.

### 1.4 Objectives
Start with the general SIWES purpose, then name three to five specific things the student intended to achieve at this particular company.

---

## CHAPTER 2 — Activity section anatomy

Each theme section (2.2, 2.3, 2.4 ...) follows this shape:

1. **Opening sentence:** What the task was and why it arose.
2. **What I did, step by step:** Named tools, commands, components, decisions. Not "I worked on it" but "I wrote a Python script using the requests library to poll the API every 30 seconds and write the response to a local SQLite database."
3. **What happened and how I knew it worked:** The outcome, verified by something measurable.
4. **Theory linkage (2–4 sentences):** State the engineering principle, show it at work in this task, and connect it to something in CE theory. Pick from the Theory Linkage Bank in SKILL.md.
5. **Personal observation (1–2 sentences):** Something only this student could write. What surprised them, what confirmed their expectations, what they would do differently.

---

## CHAPTER 5 — Conclusions and recommendations

Conclusions: what the student actually learned and delivered. Not "it was a valuable experience." What specifically changed in their understanding or capability?

Recommendations — split by audience:
- **For future interns:** one or two practical tips about preparing for this kind of placement.
- **For the company:** one constructive suggestion about how to improve the internship programme.
- **For the university / SIWES:** one observation about what theory the programme could cover better to prepare students.

---

## STRONG vs. WEAK WRITING — Examples

| Weak (cut) | Strong (keep) |
|---|---|
| "I gained valuable experience in networking." | "I spent two weeks diagnosing connectivity faults, which showed me that a duplex mismatch on a managed switch — not the firewall I assumed — was degrading throughput across the whole floor." |
| "The company uses modern technology." | "The backend ran on a microservices architecture with eight independently deployed services, each communicating over a shared message broker running RabbitMQ." |
| "I learnt about operating systems." | "Watching the system monitor while the daemon ran showed me what process scheduling looks like outside a textbook: one runaway loop consumed 94% of a core while the rest of the system sat waiting on a 2% allocation." |
| "It was challenging but rewarding." | "The hardest part was not the technical difficulty — it was explaining to a non-technical stakeholder why the fix would take three days and not three hours." |

---

## WORD COUNT TARGETS BY SECTION

| Section | Target words |
|---|---|
| Chapter 1 | 400–600 |
| Chapter 2 (all activity sections) | 1,200–1,800 |
| Chapter 3 | 300–500 |
| Chapter 4 | 400–600 |
| Chapter 5 | 200–350 |
| Chapter 6 | 300–450 |
| **Total** | **2,800–4,300** |
