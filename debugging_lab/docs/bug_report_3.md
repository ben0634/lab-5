# Lemon Clicker Bug Report

**Name:** Ben
**Tickets solved:** 3

---

## Ticket <3>: <ticket The lemon only lands in four spots
">

### Actual cause


**File / function:**

The bug was in GameScreenView.ts

**What was wrong:**

Our calculation for generating a random number only allowed for four different positions.

### Fix

<!-- What did you change, and why does that change fix the problem? -->
Since our random number generation logic was wrong, I removed math.round(). math.round() was causing our random number to become either 0 or 1, completely removing the randomness.

### How did you find it?

#### Hypothesis testing

**What hypothesis ultimately led you to identify the buggy code, and why?**

I suspected that GameScreenView.ts was most likely responsible because the screen view seemed to be what is most likely to display the lemon's position. My hypothesis was correct as I found the function randomizeLemonPosition(), which calculates the lemon's random X and random Y. I corrected the function by removing round().


### Confirming the fix

<!-- How did you confirm the problem is gone? -->
I refreshed the page, played the game, and the lemon started moving to more random positions when I clicked it.