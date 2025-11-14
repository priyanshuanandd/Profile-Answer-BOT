
# AI-Powered Personal Website Chatbot

An intelligent backend chatbot designed to handle user interactions on a personal website using OpenAI function-calling, automated logging, and real-time notifications. The system represents the website owner by ingesting their profile/summary and generating context-aware responses.

## Features

* **User Detail Capture:** Automatically records visitor email, name, and notes via Pushover notifications.
* **Unknown Question Logging:** Logs unanswered or ambiguous user queries for later review.
* **LLM Tool-Call Execution:** Uses OpenAI function calling to manage user-detail capture and question logging.
* **Dynamic System Prompt:** Builds a detailed persona using a PDF (LinkedIn) and text summary.
* **Gradio Chat Interface:** Provides a clean chat UI for real-time interaction.

## Tech Stack

* Python
* OpenAI API
* Pushover API
* PyPDF
* Gradio
* dotenv

## File Structure

```
app.py               # Main chatbot backend with tool-calling logic
me/linkedin.pdf      # PDF ingested for persona building
me/summary.txt       # Additional profile summary
```

## How It Works

1. Loads persona details from PDF + summary text.
2. Initializes an OpenAI chat loop with function-calling enabled.
3. Executes two custom tools:

   * `record_user_details`
   * `record_unknown_question`
4. Sends Pushover alerts whenever a tool is triggered.
5. Runs a Gradio chat interface for real-time interaction.

## Environment Variables

Create a `.env` file with:

```
OPENAI_API_KEY=your_key
PUSHOVER_TOKEN=your_token
PUSHOVER_USER=your_user_key
```

## Running the App

```bash
pip install -r requirements.txt
python app.py
```

Gradio will launch locally and provide a chat URL.

## Purpose

This project demonstrates an end-to-end implementation of a personalized LLM-driven agent that can handle visitors, collect lead information, and act as a representative persona on a personal website.

---
