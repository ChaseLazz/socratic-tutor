# Socratic Tutor — Claude Code Learning System

> Turn Claude Code into a strict Socratic tutor with Bloom's 2 Sigma methodology, Feynman verification, and spaced repetition.

## What It Does

This skill transforms Claude Code from a general assistant into a **one-on-one Socratic tutor**. It implements:

- **Bloom's 2 Sigma Problem** — one-on-one mastery learning
- **Feynman Technique** — role-reversal verification (learner teaches AI)
- **Spaced Repetition** — 1-day → 7-day → 30-day review scheduling
- **Adaptive Depth** — adjusts abstraction level based on learner performance
- **Objective Testing** — multiple-choice + open-ended quizzes, no self-reported scores

## Who It's For

- Self-directed learners studying books, concepts, or exam subjects
- Students preparing for standardized tests (civil service exams, CPA, IELTS, etc.)
- Anyone who wants Claude to **teach**, not just answer questions

## Quick Install

```bash
# Clone to your Claude Code skills directory
git clone https://github.com/muscle/socratic-tutor.git ~/.claude/skills/socratic-tutor
```

Or install via RED Skill (小红书): copy the skill command from the RED Skill component and paste to Claude Code.

## How It Works

### Learning Loop

```
Explain → Verify (learner restates) → Feynman Role-Reversal → Quiz → Persist
```

### Feynman Verification (3-Tier Diagnosis)

| Level | Meaning | Action |
|-------|---------|--------|
| 🔴 Critical Misunderstanding | Core concept error | Re-teach, then learner teaches again |
| 🟡 Incomplete Understanding | Missing key details | Note in score, continue |
| 🟢 Expression Optimization | Right idea, imprecise wording | Light correction, continue |

### Progress Tracking

Every knowledge atom auto-saves with YAML frontmatter:

```yaml
topic: The Art of Amplification
domain: Power Dynamics
feynman: green
quiz_score: 3/4
mastery: needs_review
last_reviewed: 2026-06-09
next_review: 2026-06-11
```

### Exam Mode

For test prep (civil service exams, CPA, IELTS, etc.):
- Topic-type identification → Framework teaching → Timed practice → Error analysis
- Wrong answers only review (correct answers never re-appear)
- Wrong answers must be correct 2 consecutive times to pass

## File Structure

```
your-learning-repo/
├── CLAUDE.md              # Copy this to your learning repo
├── rules/
│   ├── iron-rules.md      # Non-negotiable behavioral rules
│   ├── quality-gates.md   # Output quality checklist
│   └── process.md         # Task execution workflow
├── learning_progress/
│   └── INDEX.md           # Spaced repetition schedule
└── your-topic/            # One folder per subject
    └── 01.topic-name.md   # Auto-generated notes
```

## Design Principles

### Why Role-Based, Not Tech-Stack-Based

Most CLAUDE.md templates tell Claude about your tech stack. This one tells Claude **what kind of teacher to be**. The difference:

| Tech-Stack CLAUDE.md | Socratic Tutor CLAUDE.md |
|---------------------|--------------------------|
| "Use Next.js 14 with App Router" | "Never say 'do you understand?' — ask them to demonstrate" |
| "Run tests with `just test`" | "Play a naive beginner, ask 2-3 'dumb' questions" |
| "Deploy to Vercel" | "Score 🔴/🟡/🟢, re-teach on critical errors" |

### Why Rules Are Layered

```
Axioms (top-level, 9 rules)
  ↓ conflict resolution
Iron Rules (non-negotiable, 4 categories)
  ↓ behavioral boundaries
Process Rules (workflow, 3 phases)
  ↓ execution guardrails
Quality Gates (output checks, 3 gates)
```

Conflicts resolve top-down. This prevents the common problem of contradictory rules silently averaging out.

## Comparison to Other Claude Code Skills

| Feature | Generic Skill Collections | Socratic Tutor |
|---------|--------------------------|----------------|
| Focus | Tool configuration | Role identity + pedagogy |
| Verification | None | Feynman role-reversal |
| Progress Tracking | None | Spaced repetition YAML |
| Output Quality | None | Anti-AI-slop checklist |
| Multi-Agent | None | Claude (brain) / Codex (hands) division |
| Language | English-only | Chinese-native with full localization |

## Requirements

- Claude Code (or any agent supporting SKILL.md format: Codex, Cursor, OpenClaw)
- No external dependencies

## License

MIT
