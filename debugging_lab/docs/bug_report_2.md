# Lemon Clicker Bug Report

**Name:** Ben
**Tickets solved:** 2

---

## Ticket <2>: <ticket Best score always shows 0">

### Actual cause


**File / function:**

The bug was in index.ts

**What was wrong:**

The "best" result logic was wrong.

### Fix

<!-- What did you change, and why does that change fix the problem? -->
When comparing scores for the best result, we were comparing if our score was < our best score rather than > our best score.
Because of this, we were never updating best since our comparison operator was wrong.

### How did you find it?


#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** I started in MenuScreenView.ts, where I found the exact place that the text "Best" was being displayed. I learned that the text was printing the correct variable, so it had to be an issue with calculating best.<!-- what you saw, e.g. text on screen, console error -->
2. **Traced back to:** I traced where the "best" score was being stored and updated in index.ts.<!-- where that came from, e.g. a function, a request in the Network tab, a server log -->
3. **Buggy code:** I noticed that the the code was incorrectly updating best because of the incorrect comparison operator.-->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- How did you confirm the problem is gone? -->
Once I refreshed the game page, the text was correctly displaying the best score.
