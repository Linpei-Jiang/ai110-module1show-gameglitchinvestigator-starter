# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior |     Console Output / Error    | Code Location |
|-------|-------------------|-----------------|-------------------------------|---------------|
| 3,2,1 |    Higher/Lower   |    Too High     |N/A but the hint given is wrong|     app.py    |
|  -10  |   Throw an error  |    Too High     |N/A but number went below 1    |     app.py    |
|  190  |   Throw an error  |    Too Low      |N/A but number went past 100   |     app.py    |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  Gemini

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
  Telling AI to flip the output, for example the too high and too low was flipped around so it is actually correct

- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.
  Gemini used the logic of if the user gets a number out of the range it won't deduct their attempts, but I rejected it and said they should because the rules are there, the user should know what number range they have to guess from.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
  Test the bug out, for example the outcome from the game was actually flipped around so I run the game again to see if the bug still exist.

- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  That the code runs and never crashes in the terminal, there is catch statements to prevent the errors making the actual game to crash out and stop running.

- Did AI help you design or understand any tests? How?
  AI 100% did help me understand some tests for example I was a little confused about the code and AI can easily remind me and teach me how the logic behind the code works.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
  It is the way to store user information within the same session, for example the user score that ether went up or down based on the time they guessed and if they got it correct or not.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
    Write everything down, for example if there is any changes write them down before I forget about it and after all the things are done I can reflect back to see what actually was changed and maybe avoid some of the logic behind it.

- What is one thing you would do differently next time you work with AI on a coding task?
  I think I should not reply to much on AI's logic, for example the attempt idea of when user went out of range, that should still count as a attempt in my mind.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
  AI generated code can be useful but not always because AI is not always correct and the logic behind it might be confusing.
