# Lemon Clicker Bug Report

**Name:** Ben
**Tickets solved:** 5

---

## Ticket 6: My high score disappeared from the leaderboard


### Actual cause


**File / function:**

The bug was in index.tx

**What was wrong:**

We were sorting our leaderboard wrong when trying to get our top scores. The leaderboard clearly showed that we were displaying our worst scores first, rather than our best scores.

### Fix

<!-- What did you change, and why does that change fix the problem? -->
I made sure that our line:

entries.sort((a, b) => b.score - a.score); // Sort descending

correctly sorted our entries so that they would be sorted in descending order. By swapping a and b, you can change it to ascending rather than descending order.


### How did you find it?

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?**

I suspected that the bug was in index.ts because it seemed like a similar logic bug to the one displaying our best score. I searched index.ts first and found out where the leaderboard was being calculated. I found the code where entries were being pushed, sorted, and saved. 


### Confirming the fix

<!-- How did you confirm the problem is gone? -->
I refreshed the page, played the game, and saw that the highest scores were being displayed above the lower ones.