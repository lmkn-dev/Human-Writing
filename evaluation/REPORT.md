# Human Writing Skill — Exploratory Evaluation

## Scope

Five prompts were evaluated under two conditions:

- `baseline`: user prompt only
- `skill`: the same task with `SKILL.md` supplied as additional system context

The five task types were:

- school comment
- newspaper article
- business explanation
- LinkedIn post
- German casual explanation

## Recorded metric

Detector: Sapling AI Detector, accessed on 2026-09-03.

`detector_score` is the displayed `Fake` percentage and is treated only as an external classifier signal. It is not proof of authorship.

The qualitative columns in `results.csv` are intentionally blank because no independent human raters were used.

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

In this small sample, the mean external classifier score was 19.6 percentage points lower with the skill enabled.

That difference is driven almost entirely by the newspaper-article pair. The school and business cases were unchanged, while the LinkedIn case was already near zero in the baseline condition.

No conclusion about improved naturalness, voice match, genre fidelity, specificity, or meaning preservation can be drawn from this dataset because those properties were not independently rated.

The result should therefore be treated as an exploratory observation about one classifier on one small set of outputs, not as a benchmark or detector-bypass claim.

## Evaluation artifacts

- `prompts.jsonl` contains the five task prompts.
- `results.csv` contains the generated outputs, conditions, and recorded classifier scores.

## Limitations

This evaluation does not currently provide:

- repeated generations per prompt
- documented model and sampling settings
- independent human ratings
- multiple external classifiers
- a fully specified generation environment
- an automated evaluation runner

A stronger future evaluation should add those controls before making claims about writing quality or general performance.
