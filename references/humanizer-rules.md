# Humanizer rules — inline authoring guide

These rules are applied while writing, not after. They are not a separate editing step.
Every piece of prose this skill produces — logbook entries, report chapters, oral script,
slide titles, slide body text — is authored with these rules active from the first word.

The goal is writing that sounds like one specific student wrote it, not like an AI generated
a document about a student.

---

## Vocabulary ban

Never use these words or phrases in any output:

| Banned term | Why it flags AI authorship |
|---|---|
| delve | Appears in almost no pre-2023 student writing |
| tapestry | Abstract metaphor AI overuses |
| testament | Inflated significance language |
| pivotal | Inflated significance language |
| realm | Abstract metaphor |
| landscape (as metaphor) | "the technological landscape" — meaningless |
| underscores (as verb) | AI's favourite way to signal importance |
| seamless | Promotional language |
| robust (unless physical) | "robust solution" — hollow intensifier |
| leverage (verb) | Business buzzword AI inserts reflexively |
| harness | Same as leverage |
| foster | AI's favourite verb for collaborative relationships |
| multifaceted | Hollow intensifier |
| "plays a crucial role" | Extreme overuse in AI text |
| invaluable | Stacked intensifier |
| transformative | Stacked intensifier |
| unparalleled | Stacked intensifier |
| vibrant | Promotional language |
| nestled | Promotional/travel writing |
| breathtaking | Promotional language |
| groundbreaking (figurative) | Promotional language |
| renowned | Vague notability claim |
| showcasing | -ing analysis phrase AI appends |
| boasts | Copula avoidance ("boasts a" instead of "has a") |
| enduring | Inflated legacy/significance language |
| garnering | -ing analysis phrase |
| highlighting/underscoring/emphasising (sentence endings) | Superficial -ing analysis |
| fostering/cultivating/encompassing | Superficial -ing analysis |
| Additionally (opener) | Overused AI sentence opener |
| "marks/represents a shift" | Inflated significance language |

---

## Grammar and structure bans

**Em dashes (—)**
Never use. Replace with a comma, a full stop, a colon, or restructure the sentence.
Before: "The fault was clear — a loose cable caused all the problems."
After: "The fault was clear: a loose cable had disconnected the branch switch."

**Rule of three as a reflex**
Do not force every point into three parts. If something naturally has two parts, say two.
If it has four, say four.
Before: "The team valued communication, collaboration, and commitment."
After: "The team ran daily standups and expected written status updates every Friday."

**Negative parallelisms**
"It is not just X, it is Y" and "Not only X but also Y" — avoid both entirely.
Before: "This was not just a networking task; it was a lesson in systematic diagnosis."
After: "Fixing the network fault required working through each OSI layer in order, which
turned out to be a more systematic diagnosis process than I had expected."

**Bold inside paragraph bodies**
Reserve bold for table headers and section headings only. Paragraphs read well without it,
and in-text bold is a reliable AI signal.

**Inline-header bullet lists**
"- **Term:** explanation" — avoid. Write as prose or a plain table instead.
Before: "- **Postman:** Used for API testing."
After: "I tested every endpoint with Postman before integration, which confirmed the response
schema matched the frontend's expectations."

**Sycophantic openers**
No "Great question!", "Certainly!", "Of course!", "I hope this helps.", "Let me know if you
need anything else." These belong to chatbot output, not student reports or oral scripts.

**Generic positive closers**
"The future looks bright", "exciting times ahead", "a truly transformative journey", "a major
step in the right direction" — end with a concrete next fact instead.
Before: "This placement has set me on a path toward excellence."
After: "I left the placement comfortable with Linux administration and ready to tackle the
operating systems module in third year."

**Filler openers and hedges**
| Filler | Replace with |
|---|---|
| "In today's fast-paced world..." | Start with the actual fact |
| "It is worth noting that..." | Just state it |
| "In conclusion, it can be seen that..." | Just conclude |
| "Due to the fact that..." | "Because..." |
| "In order to achieve this goal..." | "To achieve this..." |
| "The system has the ability to process..." | "The system can process..." |
| "It is important to note that..." | Remove entirely or state the point directly |
| "could potentially possibly be argued" | "may affect" |

---

## Voice rules (applied while writing)

**Vary rhythm.** Some sentences are short. Others take their time moving from the problem to
the resolution, giving the reader a sense of the actual sequence. A run of sentences that all
have the same structure sounds algorithmic; break it up.

**Use first person.** "I traced the fault to..." is more honest than "The fault was traced to..."
First person signals a real person thinking, not a passive report.

**Be specific.** Every vague phrase can be replaced by something the student actually did.
"I improved performance" → "I reduced the API response time from 2,100 ms to 120 ms by
switching SQLAlchemy's loading strategy from lazy to selectin."

**React, don't just report.** "I found this aspect of the work more interesting than I
expected" or "I was surprised that the fault turned out to be at the physical layer" is more
human than neutral cataloguing of events.

**Acknowledge when things were hard.** "I spent the better part of a morning re-reading the
datasheet before I understood the register map" is honest and specific; it is also more
credible to an examiner than a narrative where everything went smoothly.

---

## The final read-through test

Read the output aloud. If any sentence could appear unchanged in another student's report,
rewrite it. If any sentence sounds like it was generated rather than remembered, make it
specific. If three consecutive sentences all have the same structure, vary them.
