<div align="center">

# 🎙️ V.I.L.E.N.A.

**My first attempt at a personal AI assistant — a Russian-speaking voice agent, written in 2021.**

![Python](https://img.shields.io/badge/Python-3.9-3776AB?logo=python&logoColor=white)
![Year](https://img.shields.io/badge/year-2021-lightgrey)
![Status](https://img.shields.io/badge/status-archived-blueviolet)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

*"This is me, around 22, trying to build my own agent."*

</div>

---

## 🌱 The origin story

Back in 2021 I wanted a computer I could just **talk to**. So I built **Vilena** — a desktop voice assistant that listened through the microphone, figured out what I meant, and did the thing: opened sites, played music, searched the web, ran a shutdown, translated a word, told me my plans.

It's naive. It's a single 370-line script with global variables everywhere, hard-coded Russian phrases, and a fuzzy-matcher instead of any real NLU. But it *worked* — and it was the first time I felt the loop of **speech → intent → action** click into place. That loop is the whole idea I've been chasing ever since.

## 🧠 What she could do

Vilena listened via `speech_recognition`, spoke back with `pyttsx3`, and matched your request against a list of known commands using `fuzzywuzzy` string similarity — so slightly-wrong phrasing still landed. Roughly:

- 👋 Greet you and respond in Russian
- 🌐 Open a browser, VK, YouTube, or the internet in general
- 🔎 Search the web (Yandex) from a spoken query
- 🎵 Play music
- 🌍 Translate a word via Google Translate
- 🛑 Shut down the computer
- 📊 Log every request to a file and read back your history / stats
- 🗒️ Read out "plans for the future" and a little `pygame` vectors note

The name doubled as her wake-word: she'd strip out *«вилена / лена / виленка»* and a few polite fillers before parsing the actual command.

## 🛠️ Built with

`Python 3.9` · `speech_recognition` · `pyttsx3` (TTS) · `fuzzywuzzy` (intent matching) · `pandas` · `tkinter` · `PyAudio` · `colorama`

## ▶️ Running it (historical)

This is a Windows-era artifact (note the bundled `PyAudio` wheel and the `shutdown /s` command). Kept here as-is for the record:

```bash
pip install SpeechRecognition pyttsx3 fuzzywuzzy pandas colorama
pip install PyAudio-0.2.11-cp39-cp39-win_amd64.whl   # bundled Windows wheel
python vilena.py
```

## 💭 What I'd do differently now

Everything, honestly — and that's the point. No globals, real intent parsing instead of fuzzy string matching, an actual tool layer, a swappable LLM doing the understanding, tests, config over hard-coded phrases. Which is more or less the list that turned into the project below.

## 👉 What it grew into

Five years later I rebuilt this idea properly — a self-hosted AI agent with a real tool layer, hot-swappable LLMs, and live integrations (calendar, Telegram, web, browser, documents):

### ➡️ **[simeonkolchin/ai-assistant](https://github.com/simeonkolchin/ai-assistant)** — *what Vilena grew into.*

Same dream, five years of learning in between.

## 📄 License

MIT © [Simeon Kolchin](https://github.com/simeonkolchin)
