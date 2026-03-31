# Groq UI Generator

A prompt-driven UI generator powered by the Groq API and `llama-3.3-70b-versatile`. Just change the prompt and it will generate any UI you want — dashboards, clocks, forms, landing pages, and more — as live rendered HTML inside a Jupyter notebook.

## How It Works

1. Loads the Groq API key from a `.env` file
2. Sends your prompt to the `llama-3.3-70b-versatile` model, which returns raw HTML/CSS/JS
3. Strips any accidental markdown formatting from the response
4. Renders the generated UI live in the notebook using IPython's `display(HTML(...))`

## Requirements

- Python 3.8+
- Jupyter Notebook or JupyterLab
- A [Groq API key](https://console.groq.com)

## Setup

1. Create and activate a virtual environment:
   ```
   python -m venv .venv
   .venv\Scripts\activate
   ```

2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

3. Create a `.env` file in the project root:
   ```
   GROQ_API_KEY=your_actual_key_here
   ```

## Usage

Open the notebook in Jupyter and run all cells:
```
jupyter notebook groq-ui-generator.ipynb
```

To generate a different UI, change the `content` field in the user message inside the notebook. For example:

- `"Create a to-do list app with a minimal dark theme and smooth animations"`
- `"Build a cryptocurrency price tracker dashboard with neon accents"`
- `"Make a retro-styled calculator with a glowing display"`
- `"Create a social media profile card with a gradient background"`
- `"Build a countdown timer with a futuristic HUD-style design"`

The model will generate pure HTML, CSS, and JS — no frameworks, no dependencies — and render it instantly in the notebook output.

## Project Structure

```
groq-ui-generator/
├── groq-ui-generator.ipynb   # Main Jupyter notebook
├── requirements.txt          # Python dependencies
├── .env                      # API key (not committed)
├── .gitignore
└── README.md
```

## Notes

- Never commit your `.env` file — it's listed in `.gitignore`
- The `display(HTML(...))` output only renders inside a Jupyter environment
- Change the prompt in the notebook to generate any UI you want
