# Lemon Clicker Bug Report

**Name:** Ben
**Tickets solved:** 1

---

## Ticket <1>: <ticket Stats always say "Stats unavailable">

### Actual cause

<!-- Which file and function was the bug in, and what was wrong with the code?
     Explain why that code produced the behavior described in the ticket. -->

**File / function:**

The bug was in MenuScreenController.ts

**What was wrong:**

The path of the api route was wrong

### Fix

<!-- What did you change, and why does that change fix the problem? -->
We were fetching stats from "/api/stat" instead of "/api/stats"
Since the path was wrong, our function was returning null which is why it always says "Stats Unavailable."


### How did you find it?


#### Backward tracing

<!-- Start from the symptom you saw and work backwards, one step at a time,
     until you reach the buggy line. For each step, note where you looked
     and what you saw there. Add steps as needed. -->

1. **Symptom:** I saw that the text displayed was "Stats Unavailable" so I traced to MenuScreenView.ts where the function updateStats() displays this text.<!-- what you saw, e.g. text on screen, console error -->
2. **Traced back to:** I traced that the function updateStats() is being called in MenuScreenController.ts, in a function called refreshStats().<!-- where that came from, e.g. a function, a request in the Network tab, a server log -->
3. **Traced back to:** refreshStats() awaits stats from a function called loadStatsFromServer, which makes the direct api call to get the stats.
4. **Buggy code:** I noticed that the api call had a typo, and fixed it.<!-- the file, function and line where the trace ended -->

<!-- It is okay to use your judgement here in limiting the number of traceback steps. We want to understand your 
    reasoning for how you discovered where the bug was -->

### Confirming the fix

<!-- How did you confirm the problem is gone? -->
Once I refreshed the game page, the text was correctly displaying the game statistics.
