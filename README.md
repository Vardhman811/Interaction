# Interaction

Yes. For your `Interaction/basic.py` script, the prerequisites are:

1. Python installed
   Use Python `3.10+` ideally. Your machine already has `3.12.3`.

2. Correct Python package installed
   You need `google-genai`.

   ```bash
   python3 -m pip install google-genai
   ```

3. A Gemini API key
   Create one from:
   https://aistudio.google.com/apikey

4. API key set as an environment variable
   In `zsh`:

   ```bash
   export GEMINI_API_KEY="your_api_key_here"
   ```

5. Internet access
   The script calls Google’s Gemini API, so it won’t work offline.

6. A supported SDK version
   For `client.interactions.create(...)`, you need a newer `google-genai` version. Your environment is now on `1.73.0`.

7. The script file itself
   Current file:
   [basic.py](/Users/vardhman/IdeaProjects/Python/Interaction/basic.py)

Run command:
```bash
python3 /Users/vardhman/IdeaProjects/Python/Interaction/basic.py
```

If you want, I can also turn this into a clean `README`-style prerequisites section for your project.
