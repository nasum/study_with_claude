Adaptively determine the next task based on LEARNING_PLAN.md evaluation and generate TASK.md. Execute the following steps in order.

## Steps

1. Read `_session/current_session.md` to confirm the current topic and latest evaluation
2. **Use a general-purpose agent to analyze learning trends** (especially effective when there are many past reviews)

   Instructions for the general-purpose agent:
   ```
   Read {topic}/LEARNING_PLAN.md and all review files under {topic}/00_reviews/,
   then report the following 3 points in 200 characters or less:

   1. [Strengths] Concepts/patterns that repeatedly received high evaluations
   2. [Weaknesses] Concepts/patterns where the user repeatedly struggled
   3. [Recommended Difficulty] Difficulty for the next task (Introductory/Fundamental/Applied) and the reason
   ```

3. Read `{topic}/LEARNING_PLAN.md` to identify the next candidate item
4. Combine the agent's trend analysis with the following logic to determine the next task:
   - Level **A** → Assign the next item from LEARNING_PLAN at normal difficulty
   - Level **B** → Assign the next item in the same phase at the same difficulty
   - Level **C** → Assign from a different angle on the same concept (similar problem, not applied)
   - Level **D** → Assign a small task to verify related concepts from the previous task
5. Read `{topic}/NN_{task_name}/TASK.md`
6. Generate the determined task's `TASK.md` at `{topic}/NN_{task_name}/TASK.md`:
   - Fill in metadata (generation date, difficulty, prerequisite task, corresponding LEARNING_PLAN item)
   - Write objective, background, and concept explanation without code
   - Write tasks and completion criteria in checklist format
7. Update `_session/current_session.md`:
   - Record the current task directory
   - Status: Assigned
   - Next action: Waiting for hints or waiting for review
8. **Explain the next task to the user in conversation** (include the reason for choosing this task)

## Constraints

- Do not write code (concept explanation only)
- Always state the reason for task selection (e.g., "Since you got B last time, I'll assign the next item in the same phase")
- Even when assigning original tasks not in LEARNING_PLAN, align them with the context of the PLAN
