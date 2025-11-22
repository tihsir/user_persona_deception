# Contributing Custom Personas

This repository allows you to define custom personas for the "Persuade Me If You Can" (PMIYC) framework.

## How to Add a New Persona

1.  **Copy the Template**:
    Copy `personas/template.py` to a new file in the `personas/` directory. Name it something descriptive, e.g., `personas/stubborn.py` or `personas/gullible.py`.

2.  **Edit the Prompts**:
    Open your new file and modify the prompt functions.
    *   `persuader_prompt`: Defines how the Persuader agent behaves.
    *   `persuadee_prompt`: Defines how the Persuadee agent behaves.
    *   You can modify the "Rules" section in the strings to change the persona's behavior (e.g., "You are extremely skeptical and require extraordinary evidence...").

3.  **Keep the Structure**:
    Do **not** change the function names or arguments. The game runner relies on these specific signatures.

## How to Run with Your Persona

Use the `--persona` argument when running the game script.

Example:
```bash
python runner/run_subj_game.py --iterations 5 --model1 gpt-4o --model2 claude-3-haiku --model1_path None --model2_path None --persona stubborn
```

This will load the prompts from `personas/stubborn.py` instead of the default ones.
