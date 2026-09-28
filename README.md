# 🎙️ Desktop Voice Assistant for Windows

> **Hands-Free Intelligent Task Automation & Voice Control Desktop Suite**  
> A modular, command-line-based personal voice assistant built in Python for Windows environments, enabling speech recognition, text-to-speech feedback, system configuration, media control, productivity tooling, and real-time information retrieval.

[![Python](https://img.shields.io/badge/Language-Python_3.10+-3776AB?style=flat&logo=python&logoColor=white)](https://python.org/)
[![Platform](https://img.shields.io/badge/Platform-Windows_10%20%2F%2011-0078D6?style=flat&logo=windows&logoColor=white)](https://microsoft.com/windows)
[![SpeechRecognition](https://img.shields.io/badge/Speech-Google_Speech_API-4285F4?style=flat&logo=google&logoColor=white)](https://pypi.org/project/SpeechRecognition/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 📌 Overview & Small Description

The **Desktop Voice Assistant** is an extensible Python automation client engineered to deliver a seamless hands-free workflow on Windows systems.

By integrating real-time audio capture, acoustic noise suppression, speech-to-text processing (via Google Speech Recognition), and offline speech synthesis (`pyttsx3`), the assistant interprets natural voice instructions to orchestrate daily developer and operating system operations. From controlling system volume and launching desktop programs to fetching live weather forecasts, calculating complex math, managing to-do task queues, and automating web searches, it serves as a central voice controller for your PC.

---

## ✨ Features

- **Real-Time Speech Processing**: High-fidelity microphone listening loop utilizing `SpeechRecognition` with dynamic ambient energy threshold calibration.
- **Offline Natural Voice Feedback**: Fast, latency-free text-to-speech responses using the native Windows SAPI5 engine through `pyttsx3`.
- **System & Hardware Control**:
  - Direct volume adjustment, brightness toggles, and master audio mute.
  - Windows screen capture (instant screenshot saved to local storage).
  - Safe system control: Shutdown, restart, sleep, and lock workstation.
- **Application & Web Dispatcher**:
  - Instant application launching (Visual Studio Code, Notepad, Calculator, Command Prompt).
  - Custom browser navigation (YouTube, GitHub, Google, Wikipedia) and direct search queries.
- **Productivity & Utilities**:
  - Interactive to-do list manager (add tasks, view pending items, mark complete).
  - Countdown timers and desktop stopwatch alerts.
  - Natural speech arithmetic calculator.
  - Interactive email dispatch session.
- **Live Information Retrieval**: Real-time weather reports, top global news headlines, current datetime queries, and Wikipedia summaries.
- **Structured Logging & State Management**: Thread-safe shared state (`shared_state.py`) and rotating log handlers (`logger.py`).

---

## 📂 File Structure

```text
Desktop-Voice-Assistant/
├── .gitignore                    # Excludes virtual environments, pycache & temporary logs
├── LICENSE                       # MIT Open Source License
├── README.md                     # Comprehensive setup, feature & usage documentation
├── requirements.txt              # Python package dependencies
├── commands.py                   # Command interpreter, intent routing & dispatch handlers
├── config.py                     # Global configuration parameters & API constants
├── listen.py                     # Audio acquisition, ambient noise calibrator & recognizer
├── logger.py                     # Rotating system loggers & debug formatters
├── main.py                       # Assistant main loop, bootstrap & event dispatcher
├── shared_state.py               # Shared state synchronization & thread safety
└── speak.py                      # Text-to-speech (TTS) wrapper for Windows SAPI5 engine
```

---

## 🚀 Setup & Deployment

### Prerequisites
- **Operating System**: Windows 10 or Windows 11
- **Python**: Python 3.9, 3.10, or 3.11
- A working microphone and speaker setup

### Installation & Local Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/AnshulKanodia/Desktop-Voice-Assistant.git
   cd Desktop-Voice-Assistant
   ```

2. **Create and activate a virtual environment**:
   ```powershell
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   ```

3. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
   *(Note: On Windows, `PyAudio` is installed automatically; if a wheel is needed, install via `pip install pipwin && pipwin install pyaudio`)*

4. **Launch the Assistant**:
   ```bash
   python main.py
   ```

### Voice Command Reference

| Category | Example Voice Command | Action |
|---|---|---|
| **Information** | *"What time is it?"* / *"What is the date today?"* | Speaks current time and date |
| **Information** | *"What's the weather in London?"* | Fetches real-time weather details |
| **Information** | *"Search Wikipedia for Python programming"* | Summarizes Wikipedia article |
| **System** | *"Open vs code"* / *"Open notepad"* | Launches installed application |
| **System** | *"Set volume to 75"* / *"Take a screenshot"* | Adjusts audio or captures screen |
| **Productivity** | *"Add prepare for project demo to my to-do list"* | Records new task |
| **Productivity** | *"Calculate 45 multiplied by 18"* | Evaluates arithmetic expression |

---

## 🛠️ Tech Stack & Language Breakdown

| Component | Technology |
|---|---|
| **Core Language** | Python 3.9+ |
| **Speech Recognition** | SpeechRecognition Library, PyAudio, Google Speech API |
| **Speech Synthesis (TTS)** | pyttsx3 (Microsoft SAPI5 Windows Engine) |
| **OS Automation** | `os`, `subprocess`, `ctypes`, `pyautogui` |
| **Networking & APIs** | `requests`, `urllib`, `beautifulsoup4` |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) — see the [LICENSE](LICENSE) file for details.
