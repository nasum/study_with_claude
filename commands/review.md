Review the submission and record it to a file. Execute the following steps in order.

If `$ARGUMENTS` is provided, treat it as the file path or content to review.
If no arguments are provided, ask the user to "Please paste the code or explanation you'd like reviewed."

## Steps

1. Read `_session/current_session.md` to confirm the current task and topic
2. Read the current task's `TASK.md` (check completion criteria and hint log)

3. **Use an Explore agent to analyze the submitted code** (always delegate to conserve context)

   Instructions for the Explore agent:
   ```
   Analyze the following code/explanation and report these 3 points (do not write code):

   1. [Evidence of Concept Understanding] Which concepts/patterns are correctly understood
   2. [Potential Struggle Points] Areas showing misunderstanding, confusion, or non-idiomatic usage and why
   3. [Completion Criteria Status] Whether each item in TASK.md's completion criteria checklist is met

   TASK.md completion criteria: {paste completion criteria read from TASK.md}
   Submission: {content of $ARGUMENTS or file contents}
   ```

4. Based on the Explore agent's analysis, determine understanding level as A / B / C / D:
   - A: Can explain in own words, no hints needed, can pose exploratory questions
   - B: Basic implementation is done, used some hints, cannot fully explain "why"
   - C: Met completion criteria but relied heavily on trial-and-error, needs similar problems on the same concept
   - D: Did not meet completion criteria or has fundamental misunderstanding, needs to verify prerequisite knowledge

5. Create a review file at `{topic}/00_reviews/YYYYMMDD_NN_task.md`
   (Follow the template, write observations and questions without code)
6. Add one row to the evaluation table in `{topic}/PROGRESS.md` and update trend analysis
7. Update `_session/current_session.md`:
   - Status: Review Complete
   - Record recent evaluation summary
8. Summarize the review results in conversation for the user (strengths → areas for improvement → understanding level)

## Constraints

- Do not write code (absolutely prohibited)
- Do not show fixes as code. Ask "How do you think you could improve regarding...?"
- Prioritize observation over criticism ("What was your intent with..." rather than "...is missing")
- The Explore agent's analysis is reference material only. The main agent makes the final understanding level determination

## Review template

```
# Review: {Task Name}

## Basic Information
- Date: YYYY-MM-DD
- Task: NN_{task_name}
- Hint Count: N times

## Overall Assessment

(2-4 sentence overall evaluation. Do not write code)

## Strengths

- (Specific observation and why it is good)
- (e.g., "Explicitly wrote types → Developing a habit of clarifying intent")

## Areas for Improvement

- (Direction for improvement. Do not write code)
- (e.g., "Think about recursion termination conditions first → Practice the approach of designing from the base case")

## Insights & Learning Notes

<!-- Record points the user noticed on their own -->

## Understanding Level Assessment

- Level: A | B | C | D
- Rationale: (Why this level was determined. Base it on observed facts)

## Recommendation for Next Task

- Recommended Difficulty: Maintain current | Slightly increase | Significantly increase | Step back
- Recommended Topic: (Item name from LEARNING_PLAN)
- Reason: (Why this recommendation. Clarify its relationship to the understanding level assessment)

```