# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
    -  I am not sure why the developers hint was added. But as a user, I could see the answer and could always guess the number in the first trial. It is not expected to see developers info on user screen.
    - List at least two concrete bugs you noticed at the start  
    - The hints are not right. They are showing arbitary.
    - The attempt left on the top did not match the actual attempts left.
    - When the hints are shown, adding a new number and clicking on submit, first cleared the hint and then I had to click on submit again to the value to be considered as my new answer.
    - Clicking on new game did not clear the previous outputs and state. Due to this even when I clicked on New Game, I was unable to actually play.
    - In the input box, it says 'Enter to apply', but the enter button doesn't work.



---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
    - Used Claude integrated with my VS Code.

- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
    - Claude gave me correct answer when I asked about the session data not synced real-time. 

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
    - It gave wrong suggestion initally when I asked it to check the update score logic. Since the attempts were incremented first, the logic Claude gave was wrong, because it always subtracted attempt * 10 points. This meant, if the user guessed answer in the first try, they will get a score of 90 instead of 100.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
    - Perfomed manual as well as pytests.
- Describe at least one test you ran (manual or using pytest) and what it showed you about your code.
    - The messages Go Higher/Lower were incorrect. Tested it manually as well as through pytest.
- Did AI help you design or understand any tests? How?
    - When prompting CLaude to generate tests, I also asked it to explain the tests to be and teach me how pytest works.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
    - st.session_state.secret = random.randint(low, high)

        This line ran every time the page reloaded, without checking if a secret already existed. So every interaction (typing, clicking anything) triggered a reload and generated a new secret.

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
    - Every time the user interacts with any element (clicks a button, types in a box), Streamlit re-runs the entire Python file from top to bottom.
    
        st.session_state is a dictionary that survives across those reruns. It's Streamlit's way of remembering things between restarts.

- What change did you make that finally gave the game a stable secret number?
    - I added the secret number to session state. And on new game, regenerated it.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects? This could be a testing habit, a prompting strategy, or a way you used Git.
    - When I didn't understand something, I first asked CLaude to explain it to me. Once I understood I moved onto finding the bugs.

- What is one thing you would do differently next time you work with AI on a coding task?
    - Spent more time reading initial code.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
    - The code generate by AI is not always perfect. We need to read the code and check if it can be improved/optimized. 
