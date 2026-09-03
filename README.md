# Human Writing

A reusable Agent Skill for producing more natural, voice-aware writing without relying on deliberate mistakes or artificial randomness.

It focuses on **voice matching, genre fidelity, sentence rhythm, specificity, and level-appropriate language**.

## Features

- matches a demonstrated writing level and voice
- reduces repetitive, template-driven prose
- varies sentence and paragraph rhythm naturally
- prioritizes concrete details over generic filler
- preserves meaning, stance, tone, and genre
- supports school, university, professional, and casual writing

## Installation

Clone the repository into a lowercase skill directory:

```bash
git clone https://github.com/lmkn-dev/Human-Writing.git human-writing
```

Then place or reference the `human-writing` directory from your agent's skills location.

The skill follows the Agent Skills `SKILL.md` format and includes the required discovery metadata in YAML frontmatter.

## Usage

Use the skill when generating or rewriting prose that should sound natural and match a specific writer, proficiency level, tone, or format.

Conceptually:

```text
user prompt
    +
human-writing/SKILL.md
    ↓
model
    ↓
output
```

No runtime dependencies are required. The skill is instruction-only.

## Validation

The skill can be validated with the Agent Skills reference tooling:

```bash
skills-ref validate ./human-writing
```

## Evaluation

The `evaluation/` directory contains a small paired exploratory evaluation across five writing tasks.

The current dataset records:

- baseline and skill-assisted outputs
- one external classifier score per output

It does **not** include independent human ratings. The classifier results therefore should not be interpreted as proof of authorship or as evidence that naturalness, voice match, or genre fidelity improved.

See `evaluation/REPORT.md` for the recorded results and limitations.

## Repository structure

```text
├── README.md
├── SKILL.md
├── LICENSE
└── evaluation/
    ├── REPORT.md
    ├── prompts.jsonl
    └── results.csv
```

## License

MIT. See [LICENSE](LICENSE).
