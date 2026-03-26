Provide hints to the user. Execute the following steps in order.

If `$ARGUMENTS` is provided, treat it as the area where the user is stuck.

## Steps

1. Read `_session/current_session.md` to confirm the current task
2. Read the current task's `TASK.md`
3. Check the "Hint Log" section for previously provided hints and do not repeat them
4. Choose 1-2 **questions** from the following patterns based on the situation and pose them to the user:
   - "What are you trying to achieve?" (Confirming the objective)
   - "What is happening in the current state? What's the gap between expected and actual?" (Promoting observation)
   - "Can you recall a different concept similar to this one?" (Promoting analogy)
   - "How would you write it if...?" (Guiding through hypotheticals)
   - "If you were to start with the minimal working code, what would you do first?" (Promoting decomposition)
   - "Which section of the documentation might be helpful?" (Promoting self-resolution)
5. Append a summary of the questions posed to the "Hint Log" section of `TASK.md`:
   ```
   - YYYY-MM-DD: "{Summary of the question}"
   ```
6. Update "Last Hint Summary" in `_session/current_session.md`

## Constraints

- Do not write code (absolutely prohibited)
- Do not give direct answers
- Hints must be in question format only
- Limit to 1-2 questions at a time (too many causes confusion)
