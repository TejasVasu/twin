# Digital Twin

A Gradio chat application that acts as an AI version of Tejas Vasudev for career-related conversations. It uses an OpenAI chat model with profile context from `summary.txt` and extracted text from `linkedin.pdf`.

## How it works

- `app.py` starts the Gradio interface and sends chat messages to OpenAI.
- `context.py` builds the system prompt from the profile summary and LinkedIn PDF.
- `tools.py` defines function tools that send Pushover notifications when a visitor shares contact details or asks a question the twin cannot answer.
- `styles.py` contains the interface styling, JavaScript, and example prompts.

## Setup

1. Create and activate a virtual environment.
2. Install dependencies:

	```bash
	pip install -r requirements.txt
	```

3. Create a `.env` file in the project directory:

	```dotenv
	OPENAI_API_KEY=your_openai_api_key
	PUSHOVER_USER=your_pushover_user_key
	PUSHOVER_TOKEN=your_pushover_application_token
	```

4. Ensure `summary.txt` and `linkedin.pdf` contain the profile data you want the twin to use.
5. Start the app:

	```bash
	python app.py
	```

Then open the local Gradio URL shown in the terminal.

## Deployment

The app can be deployed to Render as a Python web service. Use `pip install -r requirements.txt` as the build command and `python app.py` as the start command. Configure the API keys and `GRADIO_SERVER_NAME=0.0.0.0` and `GRADIO_SERVER_PORT=10000` as environment variables. See [RENDER_INSTRUCTIONS.md](RENDER_INSTRUCTIONS.md) for the full deployment guide.

Never commit `.env`, API keys, or other private profile data to a public repository. If a key is exposed, revoke it and create a replacement immediately.
