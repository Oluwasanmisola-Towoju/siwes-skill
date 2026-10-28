# Slide design reference — pptxgenjs

This file defines the design system and code templates for the SIWES slide deck.
Use the constants and slide-type functions below verbatim. The palette and fonts
are the only source of truth; do not hard-code hex values elsewhere.

---

## Constants

```javascript
const COLORS = {
  bg:        'FFFFFF',  // white — all slide backgrounds
  primary:   '1F4E79',  // navy — titles, divider slides
  accent:    '2E75B6',  // blue — sub-titles, table headers, callout borders
  body:      '2D2D2D',  // near-black — all body text
  muted:     '777777',  // grey — captions, slide numbers, citations
  highlight: 'FFF2CC',  // pale yellow — callout box fill
};

const FONTS = { face: 'Arial', title: 26, subTitle: 20, body: 20, caption: 13 };
const MARGIN = 0.5; // inches — minimum side/top margin on every slide
```

---

## Hard design limits

- Max **50 words** body text per slide (excluding title).
- Max **6 elements** per slide (bullets + images + diagrams combined).
- **One idea** per slide. If a slide exceeds the word limit, split it.
- Font size never below **18pt** for body text.
- **White background** on all content slides. No full-bleed backgrounds.
- **No decorative icons** or accent lines under titles.
- Titles are **action sentences** — subject + verb + finding (never a label like "Results").
- Ghost deck test: reading only the slide titles in order tells the complete argument.

---

## Slide type templates

### TYPE 1 — Cover slide

```javascript
// COVER SLIDE
let slide = prs.addSlide();
slide.background = { color: COLORS.primary };
slide.addText('SIWES TRAINING REPORT', {
  x: MARGIN, y: 1.0, w: 9.0, h: 0.5,
  fontSize: FONTS.caption, color: 'FFFFFF', bold: false, align: 'center',
});
slide.addText('[Student Full Name]', {
  x: MARGIN, y: 1.8, w: 9.0, h: 0.7,
  fontSize: 32, color: 'FFFFFF', bold: true, align: 'center',
});
slide.addText('[Company Name]  ·  [Department, University]  ·  [Period]', {
  x: MARGIN, y: 2.6, w: 9.0, h: 0.4,
  fontSize: FONTS.body, color: 'AECCE8', bold: false, align: 'center',
});
```

---

### TYPE 2 — Company and role (context slide)

```javascript
// CONTEXT SLIDE — "My placement at [Company]"
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title: "I spent N weeks at [Company] as a [Role]"]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
// Left column: bullet facts
slide.addText([
  { text: 'Role: ', options: { bold: true } },
  { text: '[Role title]' },
  { text: '\nCompany: ', options: { bold: false } },  // note: avoid bold-in-body pattern — use plain text
  { text: '[Company name and field]' },
  { text: '\nDuration: ', options: { bold: false } },
  { text: '[N weeks, DD Mon – DD Mon YYYY]' },
  { text: '\nDept attached to: ', options: { bold: false } },
  { text: '[Department name]' },
], {
  x: MARGIN, y: 1.2, w: 4.5, h: 2.8,
  fontSize: FONTS.body, color: COLORS.body,
  valign: 'top', bullet: false, paraSpaceAfter: 10,
});
// Right column: org chart or company photo
slide.addImage({ path: '[company_photo_or_logo.png]', x: 5.3, y: 1.2, w: 4.0, h: 2.8 });
// Caption
slide.addText('[Caption describing the image]', {
  x: 5.3, y: 4.1, w: 4.0, h: 0.3,
  fontSize: FONTS.caption, color: COLORS.muted, italic: true,
});
```

---

### TYPE 3 — Work-stream slide (with student photo)

```javascript
// WORK-STREAM SLIDE — "What I did: [domain]"
// Split layout: text left 55%, photo right 45%
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — what this work stream achieved]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
// Bullet summary (left)
slide.addText([
  { text: '• [Specific task or tool — one line]' },
  { text: '\n• [Specific task or tool — one line]' },
  { text: '\n• [Specific task or tool — one line]' },
  { text: '\n• [Specific task or tool — one line]' },
], {
  x: MARGIN, y: 1.2, w: 5.2, h: 3.0,
  fontSize: FONTS.body, color: COLORS.body, valign: 'top',
});
// Photo (right) — replace path with actual student image filename
slide.addImage({ path: '[student_photo.jpg]', x: 5.9, y: 1.2, w: 3.4, h: 3.0 });
slide.addText('[Caption: what the photo shows]', {
  x: 5.9, y: 4.3, w: 3.4, h: 0.3,
  fontSize: FONTS.caption, color: COLORS.muted, italic: true,
});
```

---

### TYPE 4 — Case study slide

```javascript
// CASE STUDY — deep dive on one incident or project
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — what the case study shows]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
// Four-cell 2x2 table: Problem | Diagnosis | Fix | Outcome
const rows = [
  ['Problem', 'Diagnosis'],
  ['Fix', 'Outcome'],
];
const cells = [
  ['[one sentence describing the fault or challenge]',
   '[what was ruled out and what was found]'],
  ['[the specific steps taken to fix it]',
   '[how it was verified and what improved]'],
];
for (let r = 0; r < 2; r++) {
  for (let c = 0; c < 2; c++) {
    const x = MARGIN + c * 4.5;
    const y = 1.3 + r * 1.7;
    // Header
    slide.addText(rows[r][c], {
      x, y, w: 4.2, h: 0.35,
      fontSize: FONTS.caption + 1, color: 'FFFFFF', bold: true,
      fill: { color: COLORS.accent }, align: 'center',
    });
    // Content
    slide.addText(cells[r][c], {
      x, y: y + 0.35, w: 4.2, h: 1.25,
      fontSize: FONTS.body - 2, color: COLORS.body,
      fill: { color: 'F0F5FA' }, valign: 'top', margin: [4, 4, 4, 4],
    });
  }
}
```

---

### TYPE 5 — Theory linkage slide

```javascript
// THEORY LINKAGE — task → principle → how it helped
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — the principle and its payoff]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
// Three-column table: Task | Concept | How it applied
const headers = ['What I did', 'Engineering concept', 'How it applied'];
const tableData = [
  ['[task]', '[principle name]', '[one-line application]'],
  ['[task]', '[principle name]', '[one-line application]'],
  ['[task]', '[principle name]', '[one-line application]'],
];
const colWidths = [2.5, 3.0, 3.5];
const xStarts = [MARGIN, MARGIN + 2.5, MARGIN + 5.5];
const headerY = 1.2;
const rowH = 0.55;
headers.forEach((h, i) => {
  slide.addText(h, {
    x: xStarts[i], y: headerY, w: colWidths[i], h: 0.4,
    fontSize: FONTS.caption + 1, color: 'FFFFFF', bold: true,
    fill: { color: COLORS.accent }, align: 'center',
  });
});
tableData.forEach((row, r) => {
  row.forEach((cell, c) => {
    slide.addText(cell, {
      x: xStarts[c], y: headerY + 0.4 + r * rowH, w: colWidths[c], h: rowH,
      fontSize: FONTS.body - 2, color: COLORS.body,
      fill: { color: r % 2 === 0 ? 'F0F5FA' : COLORS.bg }, valign: 'middle', margin: [3, 3, 3, 3],
    });
  });
});
// Worked example callout box at bottom
slide.addText('[Worked example: "A /26 mask leaves 6 host bits → 62 usable addresses..."]', {
  x: MARGIN, y: 3.7, w: 9.0, h: 0.8,
  fontSize: FONTS.body - 2, color: COLORS.body,
  fill: { color: COLORS.highlight }, line: { color: COLORS.accent, pt: 1 },
  valign: 'middle', margin: [4, 8, 4, 8],
});
```

---

### TYPE 6 — Future studies slide

```javascript
// FUTURE STUDIES — what this prepares me for
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — "This placement prepared me for [specific 300L+ topic]"]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
slide.addText([
  { text: 'What I can now do better:\n' },
  { text: '• [specific skill or understanding gained]\n' },
  { text: '• [specific skill or understanding gained]\n\n' },
  { text: 'What the placement revealed I still need:\n' },
  { text: '• [gap — course or topic not yet covered]\n' },
  { text: '• [gap — course or topic not yet covered]' },
], {
  x: MARGIN, y: 1.2, w: 9.0, h: 3.2,
  fontSize: FONTS.body, color: COLORS.body, valign: 'top',
});
```

---

### TYPE 7 — Skills gained slide

```javascript
// PROFESSIONAL COMPETENCE — skills before/after
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — "I left with N skills I did not arrive with"]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
// Two columns
const skills = [
  ['Technical skills', '[skill 1]', '[skill 2]', '[skill 3]'],
  ['Professional skills', '[skill 1]', '[skill 2]', '[skill 3]'],
];
skills.forEach((col, i) => {
  const x = MARGIN + i * 4.5;
  slide.addText(col[0], {
    x, y: 1.2, w: 4.2, h: 0.4,
    fontSize: FONTS.subTitle, color: 'FFFFFF', bold: true,
    fill: { color: COLORS.accent }, align: 'center',
  });
  slide.addText(col.slice(1).map(s => '• ' + s).join('\n'), {
    x, y: 1.6, w: 4.2, h: 2.5,
    fontSize: FONTS.body, color: COLORS.body,
    fill: { color: 'F0F5FA' }, valign: 'top', margin: [6, 6, 6, 6],
  });
});
```

---

### TYPE 8 — Conclusion slide

```javascript
// CONCLUSION
let slide = prs.addSlide();
slide.background = { color: COLORS.bg };
slide.addText('[Action title — one sentence that summarises the whole placement]', {
  x: MARGIN, y: MARGIN, w: 9.0, h: 0.55,
  fontSize: FONTS.title, color: COLORS.primary, bold: true,
});
slide.addText([
  { text: '• [Concrete takeaway 1 — specific, not "it was valuable"]\n' },
  { text: '• [Concrete takeaway 2]\n' },
  { text: '• [Recommendation for future students or the department]' },
], {
  x: MARGIN, y: 1.3, w: 9.0, h: 2.0,
  fontSize: FONTS.body, color: COLORS.body,
});
```

---

### TYPE 9 — Section divider

```javascript
// SECTION DIVIDER
let slide = prs.addSlide();
slide.background = { color: COLORS.primary };
slide.addText('[Section title — e.g., "Work Experience"]', {
  x: 1.0, y: 2.0, w: 8.0, h: 1.0,
  fontSize: 36, color: 'FFFFFF', bold: true, align: 'center',
});
slide.addText('[Section subtitle — e.g., "What I did at [Company]"]', {
  x: 1.0, y: 3.1, w: 8.0, h: 0.5,
  fontSize: FONTS.body, color: 'AECCE8', bold: false, align: 'center',
});
```

---

### TYPE 10 — Q&A slide

```javascript
// Q&A
let slide = prs.addSlide();
slide.background = { color: COLORS.primary };
slide.addText('Questions?', {
  x: 1.0, y: 1.8, w: 8.0, h: 1.0,
  fontSize: 44, color: 'FFFFFF', bold: true, align: 'center',
});
slide.addText('[Name]  ·  [Matric No.]  ·  [University]', {
  x: 1.0, y: 3.0, w: 8.0, h: 0.5,
  fontSize: FONTS.body, color: 'AECCE8', align: 'center',
});
```

---

## Slide numbering

Add a slide number to every content slide (not cover, dividers, Q&A):

```javascript
slide.addText(`${slideNumber}`, {
  x: 9.1, y: 6.8, w: 0.5, h: 0.3,
  fontSize: FONTS.caption, color: COLORS.muted, align: 'right',
});
```

---

## Node.js runner template

The student runs this file as `node generate_slides.js`:

```javascript
const pptxgenjs = require('pptxgenjs');
const prs = new pptxgenjs();
prs.layout = 'LAYOUT_WIDE'; // 13.33" x 7.5"

const COLORS = { bg:'FFFFFF', primary:'1F4E79', accent:'2E75B6', body:'2D2D2D', muted:'777777', highlight:'FFF2CC' };
const FONTS = { face:'Arial', title:26, subTitle:20, body:20, caption:13 };
const MARGIN = 0.5;

// === PASTE GENERATED SLIDE CODE HERE ===

prs.writeFile({ fileName: 'SIWES_Presentation.pptx' });
console.log('Slides saved: SIWES_Presentation.pptx');
```

Install: `npm install pptxgenjs`
