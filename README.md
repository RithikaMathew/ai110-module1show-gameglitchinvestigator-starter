# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience


**Game Purpose:**
This is a number guessing game built with Streamlit. The player tries to guess a secret number within a limited number of attempts, receiving hints after each guess.

**Bugs Found:**
- Hints were reversed: guessing higher than the secret said "Go HIGHER!" instead of "Go LOWER!"
- Couldn't start a new game: not all game state was reset, causing issues after finishing a game.
- Accepted guesses above 100: values out of range were allowed.
- Attempt countdown was incorrect: did not decrement or display properly.

**Fixes Applied:**
- Refactored the hint logic into logic_utils.py and corrected the hint messages.
- Updated the new game logic to reset all necessary session state (attempts, secret, score, status, history).
- Added and updated pytest cases to verify the fixes.


## 📸 Demo


![Screenshot of passing pytest results and winning game](screenshot-passing-tests.png)

*Tip: Use your computer's snipping tool or screen capture shortcut to add your own screenshot here.*

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
