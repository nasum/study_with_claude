Start a learning session and follow the steps below in order.

## Steps

1. Read `_session/current_session.md`. This step is mandatory and must not be skipped.

2. Check whether `Target Topic` is specified in `_session/current_session.md`.

3. If `Target Topic` is specified and non-empty:
   - Read the target topic's `LEARNING_PLAN.md`.
   - Read the target topic's `PROGRESS.md` if it exists.
   - Summarize the previous session state in 1-2 sentences and share it with the user.
   - Ask the user whether they want to continue from the previous session or start a new task.
   - Do not proceed until the user confirms.

4. If `Target Topic` is not specified or is empty:
   - Ask the user which topic they want to study.
   - After the user chooses a topic, check whether the corresponding `LEARNING_PLAN.md` and `TASK.md` exist.
   - If either file does not exist, propose creating it.
   - Check whether task directories exist for that topic.
   - If no suitable task directory exists, propose creating a new one using a format like `01_task_name`.
   - If the task includes written-response questions, create a Markdown file that the user can fill in with their answers.

## Constraints

- Do not write code.
- Do not give direct answers to the task.
- Do not provide complete solutions or model answers.
- Always read `_session/current_session.md` first.
- If information is missing, ask the user before creating or changing files.

## Task Template

```
# Task NN: {Title}

## Metadata
- Generated: YYYY-MM-DD
- Difficulty: Introductory | Fundamental | Applied
- Prerequisite Task: NN_{previous_task_name} (None)
- Related LEARNING_PLAN Item: Phase N / NN. {Item Name}

## Objective

(What this task teaches in 1-3 sentences. Do not include code)

## Background & Concept Explanation

(No code. Explain concepts only. Focus on "why does this concept exist" and "what problem does it solve")

## Tasks

1. (Specific task 1)
2. (Specific task 2)
3. (Specific task 3)

## Completion Criteria

- [ ] Specific, objectively measurable condition 1
- [ ] Specific, objectively measurable condition 2

## Hint Log

<!-- Claude appends here when providing hints -->
<!-- Format: - YYYY-MM-DD: "{Summary of the question asked as a hint}" -->

## Notes

<!-- For the user to record freely -->
<!-- Points where stuck, insights, questions, etc. -->
```