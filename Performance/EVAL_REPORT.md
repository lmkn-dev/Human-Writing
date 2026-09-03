# Human Writing Skill — Paired Evaluation

## Scope

Five prompts were run in two conditions:

- `baseline`: prompt only
- `skill`: the uploaded `SKILL.md` supplied as additional system context

The same five task types were used in both conditions: school comment, newspaper article, business explanation, LinkedIn post, and German casual explanation.

## Detector

Detector: Sapling AI Detector, accessed on 2026-09-03.

`detector_score` is the displayed `Fake` percentage, interpreted here as the detector's AI-probability signal. It is not proof of authorship. The qualitative rating columns are intentionally blank because no independent human raters were used.

## Results

| Case | Baseline | With skill | Delta (skill − baseline) |
|---|---:|---:|---:|
| School comment | 100.0% | 100.0% | 0.0 pp |
| Newspaper article | 100.0% | 1.3% | −98.7 pp |
| Business explanation | 100.0% | 100.0% | 0.0 pp |
| LinkedIn post | 0.0% | 0.8% | +0.8 pp |
| German explanation | 100.0% | 99.7% | −0.3 pp |
| **Mean** | **80.0%** | **60.4%** | **−19.6 pp** |

## Interpretation

The skill lowered the mean detector score by 19.6 percentage points in this small sample, but the result is driven almost entirely by the newspaper pair. It did not lower the score for the school or business text, and the LinkedIn score was already near zero without the skill.

The useful conclusion is therefore not that the skill reliably bypasses a detector. It appears to improve genre fit and naturalness in some cases, while detector behavior remains inconsistent across genres and languages. More prompts, repeated generations, and independent human ratings would be needed for a stronger claim.

## Reproduction

The complete text and scores are in `results.csv`. To summarize the CSV with the supplied runner, place the uploaded `SKILL.md` at the runner's expected root and run:

```bash
python eval/run_eval.py --results eval/results.csv --summarize
```

