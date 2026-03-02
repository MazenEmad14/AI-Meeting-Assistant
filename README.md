# 🎙️ AI Meeting Assistant (Multi-Agent System)

A powerful, automated meeting assistant built with **Python** and **Streamlit**. This application processes meeting audio, transcribes it, and uses a team of AI agents orchestrated by **CrewAI** to summarize the discussion, extract action items, and automatically dispatch follow-up emails.

## 🌟 Key Features

* **Flexible Audio Input:** Supports direct audio file uploads (`.mp3`, `.wav`, `.m4a`) or downloading audio directly from YouTube URLs using `yt-dlp`.
* **Local Audio Transcription:** Utilizes Hugging Face's `transformers` with the `openai/whisper-tiny` model for accurate speech-to-text conversion.
* **Multi-Agent AI Pipeline:** Powered by **CrewAI** and Google's **Gemini 2.0 Flash**, featuring four specialized agents:
  1. **Summarizer Agent:** Extracts key decisions, discussions, agreements, and risks into structured markdown.
  2. **Action Extractor Agent:** Identifies action items, task owners, and deadlines, outputting them in a strict JSON format.
  3. **Email Drafter Agent:** Crafts a professional, context-aware follow-up email combining the summary and tasks.
  4. **Mailer Agent:** Uses a custom `MailerTool` to automatically send the drafted email to recipients via Gmail SMTP.
* **Interactive UI:** A clean Streamlit sidebar allowing users to toggle specific AI tasks (Summarize, Extract Actions, Draft Email, Send Email) and configure SMTP settings on the fly.

## 🛠️ Technology Stack

* **Frontend:** Streamlit
* **AI Orchestration:** CrewAI, LangChain
* **LLM:** Google Gemini (`gemini-2.0-flash`) via `langchain_google_genai`
* **Speech-to-Text:** Transformers (`openai/whisper-tiny`), PyTorch
* **Utilities:** `yt-dlp` (YouTube downloading), `smtplib` (Email sending), `pydantic` (Schema validation)
