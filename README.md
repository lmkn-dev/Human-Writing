# Human Writing Skill

A reusable writing skill for LLM agents focused on **voice matching, natural sentence rhythm, genre fidelity, and stylistic specificity**.

The skill helps reduce generic, overly polished, or template-driven model prose while preserving the writer's intended meaning, level, tone, and format.

## Overview

`SKILL.md` provides guidance for generating or rewriting text with a stronger sense of authorship. Its main principles include:

- matching the writer's demonstrated language level and voice
- varying sentence and paragraph rhythm naturally
- preferring concrete details over generic filler
- reducing excessive signposting and repetitive structures
- avoiding unnecessary sophistication and stock model phrasing
- preserving the user's stance, meaning, and requested genre
- keeping school writing plausible for the student's actual level

The objective is better writing quality and stylistic fit, not deliberate grammar degradation or guaranteed detector avoidance.

## Repository structure

```text
Human-Writing/
├── README.md
├── SKILL.md
└── evaluation/
    ├── REPORT.md
    ├── prompts.jsonl
    └── results.csv
```

## Usage

Load `SKILL.md` as an agent skill or include its instructions in the system or context layer before generating text.

Conceptually:

```text
Baseline
user prompt -> model -> output

With skill
SKILL.md + user prompt -> same model/settings -> output
```

For comparisons, keep the model, sampling settings, token limits, and user prompt consistent between conditions.

## Evaluation

The `evaluation/` directory contains a small paired comparison across five writing tasks:

- school comment
- newspaper article
- business explanation
- LinkedIn post
- German casual explanation

Each task has a baseline output and a corresponding output generated with the skill, for ten recorded outputs in total.

`results.csv` contains the generated text and recorded detector scores. `REPORT.md` summarizes the comparison and its limitations. The detector signal is treated as a noisy external measurement rather than proof of authorship.

The current sample is intentionally small and should not be interpreted as a benchmark of general model performance. A stronger evaluation would require repeated generations, documented model settings, broader prompts, and independent human ratings.

## Evaluation criteria

Useful criteria for future evaluations include:

| Metric | Question |
|---|---|
| Voice match | Does the output plausibly match the requested writer? |
| Genre fidelity | Does it follow the requested format and conventions? |
| Specificity | Does it use concrete details instead of generic filler? |
| Natural rhythm | Does sentence and paragraph structure vary naturally? |
| Meaning preservation | Does the rewrite preserve the requested content? |
| External classifier signal | What score does an external detector return, if measured? |

## Design principle

A strong result should not merely produce a lower classifier score. It should read more naturally, fit the requested voice and genre more closely, and preserve the underlying meaning.

## Status

This repository contains the current skill definition and a small recorded evaluation set. It does not include an automated evaluation runner.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
