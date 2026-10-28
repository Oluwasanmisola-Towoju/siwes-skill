# SIWES Complete Package Generator — Skill Bundle

**Version:** 2.0.0
**For:** 200L Computer Engineering students, Nigerian universities
**Produces:** Logbook + Training Report + Oral Script + Slide Deck in one session

---

## What this skill does

When installed in Claude, this skill runs a complete SIWES package generation pipeline.
The student answers five intake questions, then Claude produces all four deliverables at once:

| Output | Marks |
|---|---|
| Dated logbook (30 × working days) | 30 |
| Technical training report (~7,500 words) | 30 |
| Oral script (what to say slide by slide) | — |
| pptxgenjs slide deck code (beautiful, photo-matched) | 40 |

All text passes through inline humanizer rules — no AI vocabulary, no em dashes, plain
authentic student voice.

---

## Installation

1. In Claude, go to **Settings → Skills → Install from folder**.
2. Select this folder (`siwes-v2/`).
3. The skill will appear as **siwes-200l-comp-eng**.
4. Start a new chat and the intake form appears automatically.

---

## File structure

```
SKILL.md                         ← Main orchestrator (the skill entry point)
README.md                        ← This file
references/
  assessment-criteria.md         ← Official rubric (30 + 30 + 40 marks breakdown)
  report-structure.md            ← Chapter structure, word budgets, build order
  writing-style.md               ← Voice, rhythm, British/Nigerian English rules
  logbook-rules.md               ← Entry format, placement arc, illustration rules
  field-profiles.md              ← 10 domain profiles + role modifiers for gap-filling
  theory-linkage-bank.md         ← Pre-built principle sentences by engineering area
  activity-archetypes.md         ← 7 weekly activity patterns for variety
  slide-design.md                ← pptxgenjs palette, font constants, 10 slide templates
  humanizer-rules.md             ← Vocabulary ban, grammar bans, voice rules
```

---

## How to use the slides output

The oral script and slide code are delivered together in one file.

1. On your computer, create a folder and run: `npm install pptxgenjs`
2. Create `generate_slides.js` using the runner template at the bottom of `slide-design.md`.
3. Paste the generated slide code between the constant declarations and the `writeFile` call.
4. Replace image paths with the actual paths to your SIWES photos on your computer.
5. Run: `node generate_slides.js`
6. Open `SIWES_Presentation.pptx` in PowerPoint or LibreOffice Impress.

---

## Marks optimisation

The skill targets maximum marks in every sub-criterion. Key features:

- **Logbook neatness (5 marks):** Fixed table format, consistent date style, supervisor
  sign-off line every week.
- **Logbook technical content (10 marks):** 45–90 word entries with action, tools,
  validation. Informal notes upgraded to logbook grade.
- **Report technical content (10 marks):** Chapter 3 with numbered procedures and 2–3
  case studies. Minimum 6 figures and 4 tables.
- **Theory linkage (5 marks each — report and oral):** Pre-built principle sentences
  adapted to the student's real activities. Two worked examples with actual maths/logic.
- **Oral presentation technique (10 marks):** Ghost deck test (titles tell the complete
  story), one idea per slide, student photos on matching slides, timed oral script.
- **Originality (5 marks):** Every sentence built from the student's own evidence. Human
  voice rules applied throughout. No AI vocabulary.

---

## Review sheet

The first output is always `00_Review_Sheet.md`. It lists:
- Every drafted (D) item — what to read and confirm before the supervisor signs the logbook.
- Every `[Student to confirm: ...]` item — facts that need checking.
- Any photos that could not be matched to a slide.
- Assumptions made when evidence was thin.

**Read the review sheet before submitting anything.**
# siwes-skill
