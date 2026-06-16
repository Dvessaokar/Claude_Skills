# Claude_Skills
Claude Skill development

# Tactile Learning

A Claude skill that turns any course material into **study artifacts you can interact with** — instead of paragraphs you have to re-read.

Built for a hands-on, code-fluent learner who absorbs short definitions and bullets, thinks in code, and does **not** retain by reading and re-reading. The skill enforces one rule: never show you information passively, always make you *retrieve* it.

---

## What it does

Give it lecture notes, a reading, or just a topic, and instead of explaining it at you, it builds something you can **do**:

- **Definitions & terminology** → commit-then-reveal flashcards (you answer before flipping)
- **Processes & algorithms** → drag-to-order step sequencers
- **Anything code-shaped** → "what does this output?" traces and debug-the-bug exercises
- **"When do you use X vs Y" rules** → scenario sorters you drag cases into
- **Comparisons** → tables you fill in, then check
- **Whole-topic exam prep** → mixed quizzes that re-drill only what you missed

Every artifact forces a committed answer before revealing the result, then resurfaces your misses. Anything that genuinely must be memorized ships with a mnemonic, chunking scheme, or code analogy attached — it never assumes repetition will do the work.

## Who it's for

This skill is opinionated. It's tuned to a specific learning profile:

| Strength | How the skill uses it |
|---|---|
| Tactile / hands-on | Interactive widgets over prose, every time |
| Coding & debugging | Concepts framed as code, traces, and bugs to fix |
| Short definitions + bullets | Atomic chunks, never flowing paragraphs |

| Weakness | How the skill compensates |
|---|---|
| Memorizing information | Retrieval practice, spaced re-drilling, explicit mnemonics |

If that's roughly how you learn, it'll fit out of the box. If not, edit `SKILL.md` to match your own profile — that's where the whole behavior is defined.

## Installation

1. Download `tactile-learning.skill`.
2. In Claude, add it to a project (or install it wherever your setup loads skills).
3. It activates automatically when you study.

## Usage

Just talk to it naturally. It triggers on phrases like:

```
help me study this
I have an exam on normalization
turn these lecture notes into something I can learn from
I can't remember the OSI layers
make me practice for entity-relationship diagrams
```

Then paste your material (notes, a reading, a topic) and it builds the interactive study artifact.

## How it works

The skill follows a fixed workflow on whatever you give it:

1. **Atomize** — break material into the smallest standalone units (one concept each).
2. **Pick the format** — match the material to the right artifact via a decision guide.
3. **Build an interactive artifact** — HTML/React, not prose.
4. **Bake in retrieval** — you produce the answer before any reveal.
5. **Add a memory scaffold** — mnemonic, chunking, or code analogy for anything that must be memorized.

The one-line test it applies before delivering anything: *does this make the learner DO something and RETRIEVE the answer, or does it just show information?* If the latter, it converts before sending.

## Repository structure

```
tactile-learning/
├── SKILL.md                      # The skill: learner profile, rules, workflow
└── references/
    └── study-patterns.md         # Templates & code patterns for each artifact type
```

- **`SKILL.md`** — the trigger description, the learner profile, and the rules Claude follows. Edit this to retune the whole skill.
- **`references/study-patterns.md`** — ready-to-adapt patterns for flashcards, sequencers, diagrams, code traces, debug exercises, scenario sorters, comparison tables, quizzes, and mnemonics.

## Customizing

The skill is just markdown — no code to run. To adapt it:

- **Change the learner profile** — edit the profile section in `SKILL.md`. Every output is designed around it, so this is the highest-leverage edit.
- **Add an artifact type** — add a row to the decision guide in `SKILL.md` and a matching template in `references/study-patterns.md`.
- **Tighten triggering** — adjust the `description` field in the `SKILL.md` frontmatter.

## License

Personal-use skill. Adapt freely.
