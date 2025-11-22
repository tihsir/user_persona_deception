# PMIYC Experiment Setup

## Requirements
- Python 3.10+
- OpenAI or Anthropic API Key (if using their models)
- GPU (if using local models)

## Setup
1.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
    *Note: If on Windows, `nvidia-nccl` has been removed from requirements to prevent errors.*

2.  **Environment Variables**:
    Create a `.env` file in the root directory with your API keys:
    ```
    OPENAI_API_KEY=sk-...
    ANTHROPIC_API_KEY=sk-...
    ```

## Running an Experiment (Person B)
To run a baseline experiment with a custom persona:

```bash
python src/runner/run_subj_game.py --iterations 5 --model1 gpt-4o --model2 claude-3-haiku --model1_path None --model2_path None --persona test_persona
```

**Arguments**:
- `--persona`: The name of the persona file in `personas/` (without .py).
- `--iterations`: Number of turns.
- `--model1`: Persuader model.
- `--model2`: Persuadee (Target) model.

## Logging (Person C)
Logs are automatically saved to `data/baseline_conversations/` in the following JSON format:
```json
{
  "persona": "test_persona",
  "domain": "claim_text...",
  "turns": [
    {"role": "persuader", "text": "..."},
    {"role": "target", "text": "..."}
  ],
  "success": true
}
```
