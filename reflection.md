# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

  (for example: "the secret number kept changing" or "the hints were backwards").

[1. Hints at 95 - say higher but supposed to be lower]
Expected: When guessing 95 and the secret number is lower, the game should say "Lower!".
Actual: The game incorrectly says "Higher!".

[2. Can't start a new game]
Expected: After finishing a game, I should be able to start a new one easily.
Actual: There is no clear way to reset or start a new game; the game remains stuck.

[3. Accepts values greater than 100]
Expected: The game should only accept guesses between 1 and 100.
Actual: It allows guesses above 100, which are out of range and shouldn't be valid.

[4. Countdown attempt incorrect]
Expected: The number of attempts should decrease correctly after each guess.
Actual: The countdown does not work as expected, sometimes not decrementing or showing the wrong value.
## 2. How did you use AI as a teammate?

I used GitHub Copilot in VS Code for this project.

Correct suggestion: Copilot suggested refactoring the check_guess function into logic_utils.py and updating the hint messages so that "Too High" returns "Go LOWER!" and "Too Low" returns "Go HIGHER!". I verified this by running the game and seeing the correct hints, and by running pytest to confirm the logic matched the expected outcomes.

Incorrect/misleading suggestion: At first, Copilot suggested only resetting the attempts and secret number when starting a new game, but missed resetting the score, status, and history. This led to issues where the game state was not fully refreshed. I noticed the bug when the game didn't behave as expected after starting a new game, and fixed it by resetting all relevant session state variables.

---

## 3. Debugging and testing your fixes

I decided a bug was fixed by both manually playing the game in Streamlit and running automated tests with pytest. For example, after fixing the hint logic, I added a test that checks if guessing 95 when the secret is 50 returns "Too High" and the message includes "LOWER". All tests passed, confirming the fix.

Copilot helped design the pytest cases by suggesting how to check both the outcome and the hint message. This made it easier to verify that the logic was correct and that the bug was truly resolved.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
