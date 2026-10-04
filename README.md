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

The purpose of the game is for users to guess the correct numbers between a range of numbers, the target number is randomly generated and each round is different.

Bugs fixed:
- Swapped hints: check_guess said "Go HIGHER" for guesses above the
  secret and "Go LOWER" for guesses below it. Messages now point the
  correct way.
- Secret was converted to a string on even attempts, making
  comparisons unreliable. It now stays an int throughout.
- Guesses had no bounds. Negative or too-large numbers are now
  rejected with a message showing the valid range. Out-of-range
  guesses still consume an attempt (the range is displayed, so that
  is on the player); non-numeric input does not.
- Changing difficulty didn't change the game: the secret was only
  picked once and the prompt hardcoded "1 and 100". The game now
  restarts on difficulty change and the prompt shows the real range
  (Easy 1-20, Normal 1-100, Hard 1-50).
- New Game always picked from 1-100 and left score, history, and
  win/lose status untouched. It now resets everything using the
  current difficulty's range.
- Attempts started at 1, so "Attempts left" was off by one. They now
  start at 0.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. Swapping hints, the original hint was flipped, now the "Go LOWER" and "Go HIGHER" hint is actually correct.
2. There is some cases that the int are changed to String, making it wrong when comparing the target and the guess from the user.
3. There wasn't boundaries to the guesses user can put, after adding that it will show as an error if user go under or over the limits.
4. When changing diffitculty, the range didn't change before but now it changes.

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
python -m streamlit run app.py

  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8505
  Network URL: http://192.168.0.221:8505

  For better performance, install the Watchdog module:

  $ xcode-select --install
  $ pip install watchdog
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
