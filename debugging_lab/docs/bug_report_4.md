# Lemon Clicker Bug Report

**Name:** Ben
**Tickets solved:** 4

---

## Ticket <3>: <ticket Stuck on the Game Over screen
">

### Actual cause


**File / function:**

The bug was in GameScreenController.ts

**What was wrong:**

We were not stopping the timer properly when ending the game. Because the timer wouldn't reset, it would continue processing that the game was ending and keep playing the Game Over sound.

### Fix

<!-- What did you change, and why does that change fix the problem? -->
There was a typo in the code. We had "this.stopTimer" instead of "this.stopTimer()" so the function was not being called correctly.

### How did you find it?

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?**

I suspected that the bug had to do with whatever function was ending the game / resetting our timer, scores, and other values. I looked to Results screen files but couldn't find anything at first, but quickly found that GameScreenController contained logic for ending the game in function endGame(). I spotted that we were missing "()" to call the function.


### Confirming the fix

<!-- How did you confirm the problem is gone? -->
I refreshed the page, played the game, and the game would end properly -- it would not keep refreshing and playing the sound.