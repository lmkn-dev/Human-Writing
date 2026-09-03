# Human Writing Skill

A reusable writing skill for LLM agents that improves **voice matching, natural sentence rhythm, genre fidelity, and stylistic specificity** without deliberately degrading grammar or inserting fake mistakes.

The skill is designed for situations where generic model prose feels too polished, repetitive, abstract, or template-driven.

## What it does

`SKILL.md` instructs an agent to:

- match the writer's demonstrated level before "improving" it
- vary sentence rhythm and paragraph shape
- prefer concrete details over generic filler
- reduce excessive signposting and symmetrical argument structures
- avoid fake sophistication and stock AI phrasing
- preserve the user's actual stance and genre
- keep school writing plausible for the student's level

The goal is **natural authorship**, not detector evasion.

## Repository structure

```text
human-writing-skill/
├── README.md
├── SKILL.md
└── eval/
    ├── prompts.jsonl
    ├── run_eval.py
    └── results_template.csv
```

## Usage

Load `SKILL.md` as an agent/Claude skill or add its instructions to the system/context layer before generating the requested text.

Conceptually:

```text
BASELINE
user prompt -> model -> output

WITH SKILL
SKILL.md + user prompt -> same model/settings -> output
```

For a meaningful comparison, keep the **model, temperature, max tokens, and user prompt identical** between baseline and skill runs.

## Evaluation

The included eval uses five writing tasks. Each task is generated twice:

- **5 baseline outputs** — model without `SKILL.md`
- **5 skill outputs** — same model with `SKILL.md`

This gives 10 outputs total.

The harness is designed to record an external checker's score alongside human-oriented writing metrics. Because proprietary AI-detection systems can change and may produce false positives, their score should be treated as **one noisy measurement**, not ground truth.

Recommended metrics:

| Metric | What it tests |
|---|---|
| Detector score | External classifier signal, if available |
| Voice match | Does it plausibly match the requested writer? |
| Genre fidelity | Does it actually read like the requested format? |
| Specificity | Does it use concrete details instead of generic filler? |
| Natural rhythm | Is sentence/paragraph structure varied without forced randomness? |
| Meaning preservation | Did style changes alter the requested content? |

### Run the eval

```bash
python eval/run_eval.py
```

By default the script builds the 10-case evaluation manifest and writes a CSV you can fill with outputs and checker scores.

You can also pass generated outputs back into the CSV and calculate paired summary statistics:

```bash
python eval/run_eval.py --results eval/results.csv --summarize
```

## Interpreting results

The strongest result is **not** simply "lower AI probability." A good skill should improve human ratings for voice, specificity, rhythm, and genre while preserving meaning.

A detector-only win can be misleading: detectors are probabilistic, model-dependent, and can misclassify both human and AI-written text.

## Example hypothesis

> Adding the Human Writing Skill will reduce generic model-writing patterns and improve human-rated naturalness and voice consistency compared with the same model generating from the user prompt alone.

## Reproducibility notes

When publishing results, record:

- model + exact version
- date of test
- temperature / sampling settings
- checker name + version/date
- raw outputs
- raw checker scores
- human rating rubric

Do not cherry-pick prompts or rerun only the cases where one condition performs poorly.

## License

Add the license that fits your intended use. MIT is a common choice for a small public prompt/agent-skill repository.
