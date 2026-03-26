# Study with Claude

An interactive programming learning repository using Claude Code as an **Examiner, Hint Guide, and Reviewer**.

## Overview

Claude Code adaptively assigns tasks based on the learner's understanding level, provides hints in question format to encourage thinking, and reviews submissions to determine the next step. It never provides code or direct answers.

## Learning Flow

```
Session Start → Task Assignment → Implementation → (Hints) → Review Submission → Evaluation → Next Task
```

1. Run `/start` to begin a session and restore the previous state
2. Claude assigns a task based on LEARNING_PLAN.md
3. The learner implements on their own (use `/hint` for question-style hints when stuck)
4. Run `/review` to request a review and receive an A–D understanding level evaluation
5. Run `/next` to proceed to the next task based on the evaluation

## Slash Commands

| Command | Description |
|---------|-------------|
| `/start` | Start session / restore state |
| `/hint [where you're stuck]` | Provide hints in question format |
| `/review [file path or content]` | Review submission and save evaluation |
| `/next` | Adaptively determine and assign the next task |
