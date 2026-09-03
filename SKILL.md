# Human Writing Skill

## Purpose

Produce writing that feels natural, personal, and appropriately imperfect instead of polished in a generic AI style.

The goal is **not** to intentionally make writing bad. The goal is to preserve human rhythm, variation, specificity, and the writer's actual level.

Use this skill when the user asks for:
- school or university writing
- emails, messages, posts, comments, or essays
- rewrites that should sound less AI-generated
- writing that should match an existing personal style or proficiency level

---

## Core Principles

### 1. Match the writer before improving the writer

Do not automatically upgrade vocabulary, grammar, structure, or argumentation beyond the user's likely level.

Preserve:
- vocabulary range
- sentence complexity
- tone
- confidence level
- typical phrasing
- degree of formality

If samples of the user's writing are available, treat them as the primary style reference.

### 2. Vary sentence rhythm

Avoid a sequence of equally sized, perfectly structured sentences.

Mix:
- short statements
- medium explanatory sentences
- occasional longer sentences
- fragments when natural for the format

Human writing often changes pace depending on what matters.

### 3. Prefer ordinary words

Use the simplest word that expresses the intended meaning well.

Avoid unnecessary AI-favored wording such as:
- furthermore
- moreover
- multifaceted
- crucial
- pivotal
- underscores
- delves into
- serves as a testament
- in today's rapidly evolving world

Do not ban these words mechanically. Use them only when they genuinely fit the writer and context.

### 4. Avoid template prose

Do not force every piece into:
1. broad introduction
2. three balanced arguments
3. generic conclusion

Structure should follow the actual task.

Avoid repetitive patterns such as:
- "This shows that..."
- "Another important aspect is..."
- "In conclusion..."
- "On the one hand... on the other hand..." repeated mechanically

### 5. Use concrete details

Specific details make writing feel authored rather than generated.

Prefer:
- exact observations
- examples from the supplied material
- direct references to events, scenes, numbers, or arguments

Avoid padding with broad statements that could fit any topic.

### 6. Allow controlled imperfection

Only when appropriate to the user's level and explicit request, retain small human imperfections.

Acceptable imperfections can include:
- slightly informal transitions
- occasional repeated simple words
- a sentence that is not maximally elegant
- minor stylistic awkwardness
- natural contractions in English

Do **not** deliberately introduce errors merely to evade AI detection.

If the user explicitly requests intentional mistakes, prefer authentic level-matching over artificial errors. Do not add errors that change meaning, make the text confusing, or materially reduce quality.

### 7. Do not over-explain

Humans frequently leave obvious connections implicit.

Do not add a sentence explaining every previous sentence.

Example:

Overwritten:
> The character leaves the house because he feels uncomfortable. This demonstrates that he is emotionally distressed and therefore wants to escape the situation.

More natural:
> He leaves the house because he feels uncomfortable and wants to get away from the situation.

### 8. Avoid fake sophistication

Do not make an argument appear deeper by replacing clear reasoning with abstract nouns.

Prefer:
> The company can produce more cheaply because wages are lower.

Instead of:
> The corporation benefits from cost-efficiency dynamics resulting from disparities in international labor expenditure.

### 9. Preserve personal stance

If the user has a clear opinion, retain it.

Do not neutralize strong but reasonable positions into generic balanced prose unless the task requires neutrality.

Use first-person language when appropriate:
- I think
- in my view
- what I found interesting was

Do not overuse it.

### 10. Write for the actual medium

A newspaper article should read like a newspaper article.
A school comment should read like a school comment.
A LinkedIn post should not sound like an essay.
A message should not sound like a press release.

Follow genre conventions before stylistic beautification.

---

## Anti-AI Style Checks

Before finalizing, check for these failure modes.

### Remove excessive symmetry

AI often creates exactly three equally developed points. Keep symmetry only when the task benefits from it.

### Remove unnecessary signposting

Delete phrases whose only purpose is announcing the next sentence.

Examples:
- "It is important to note that"
- "It should also be mentioned that"
- "Another key point to consider is"

### Reduce adjective stacking

Avoid constructions like:
> an innovative, transformative, powerful and highly effective approach

Choose the one or two adjectives that matter.

### Remove generic conclusions

Avoid endings such as:
> Only time will tell how this issue develops in the future.

Finish with the actual point.

### Break predictable paragraph rhythm

Do not make every paragraph:
- topic sentence
- explanation
- example
- mini-conclusion

Natural paragraphs can have different internal shapes.

---

## School Writing Mode

When writing for school:

1. Match the student's demonstrated language level.
2. Use terminology that has plausibly been covered in class.
3. Do not introduce university-level concepts solely to impress.
4. Prefer straightforward analysis over ornamental language.
5. Base claims on the material the student actually has.
6. Do not pretend the student has read or watched material they have not encountered.
7. Keep grammar mostly correct while allowing natural non-native phrasing when that matches the student's level.
8. Follow the requested genre exactly: comment, article, analysis, speech, etc.

### Example

AI-like:
> The movie masterfully explores the multifaceted nature of interpersonal relationships, ultimately underscoring the complexity of human affection.

Human/student-like:
> The movie shows that relationships can get complicated, especially when people do not feel the same way about each other.

---

## Rewrite Procedure

When transforming existing text:

### Step 1 — Extract meaning
Identify the claims, facts, opinion, and required information. Do not change these unnecessarily.

### Step 2 — Infer voice
Estimate:
- age / proficiency if relevant and known
- formality
- vocabulary level
- typical sentence length
- confidence

### Step 3 — Rewrite from meaning
Do not merely substitute synonyms sentence by sentence. Reconstruct the passage naturally.

### Step 4 — De-polish selectively
Remove:
- generic transitions
- excessive abstraction
- repeated rhetorical structure
- unnecessarily formal wording

### Step 5 — Read aloud test
Ask internally:
> Would a real person at this level plausibly say or write this?

If not, simplify or restructure.

---

## Output Rules

Unless the user requests otherwise:

- Keep the requested length.
- Preserve all factual requirements.
- Do not mention that the text was made to appear human.
- Do not claim that text is "undetectable" or guaranteed to bypass AI detectors.
- Do not use deliberate misspellings as a default technique.
- Prefer authenticity over artificial randomness.

---

## Optional Style Parameters

A calling agent may provide:

```yaml
writer_level: secondary-school | university | professional | custom
language: en | de | other
formality: casual | neutral | formal
imperfection: none | light | natural
sentence_complexity: simple | mixed | advanced
preserve_voice: true
strict_genre: true
```

Interpret these as tendencies, not rigid generation settings.

---

## Quality Standard

A successful result should feel like someone had a clear thought and wrote it themselves.

It should **not** feel like an AI tried to simulate a human by randomly making mistakes.
