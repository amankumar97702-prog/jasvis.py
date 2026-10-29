# Jasvis AI Assistant

A Windows-friendly Python desktop assistant with voice input, spoken replies, website opening, online Gemini chat, a simple animated avatar, and SQLite conversation history.

## Features
- Desktop GUI with animated pulse avatar
- Voice input (Hindi-first, then English-India fallback)
- Text-to-speech using installed Windows voices
- Open common sites or any domain: `open youtube`, `open wikipedia`, `open example.com`
- Unknown spoken/text requests go to Gemini AI chat
- Conversation messages stored locally in `jasvis_memory.db`
- Stop voice listening and exit commands

## Requirements
- Windows 10/11 recommended
- Python 3.10 or newer
- Internet connection for speech recognition and Gemini chat
- Microphone and speakers
- A Gemini API key for online AI chat

## Install (Windows)
1. Extract the ZIP to a normal folder.
2. Open Command Prompt in that folder.
3. Create and activate a virtual environment (recommended):
   ```bat
   py -m venv .venv
   .venv\Scripts\activate
   ```
4. Install packages:
   ```bat
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```
   If `PyAudio` installation fails, install a compatible wheel for your Python version or use `pip install pipwin` and follow its current instructions.
5. Set a Gemini API key for this terminal session:
   ```bat
   set GEMINI_API_KEY=YOUR_GEMINI_API_KEY
   ```
   Get a key from Google AI Studio. Do not share it or put it in public source code.
6. Start:
   ```bat
   python main.py
   ```

## Use
- Click **ðŸŽ™ Voice**, then speak a command.
- Try `open youtube`, `open google`, `open example.com`, `open chatgpt`, or `search for weather in Ludhiana`.
- Type a question in the input box to chat with Gemini.
- Type `exit` or `close Jasvis` to quit.
- Conversation history is stored in `jasvis_memory.db` in this folder.

## Hindi voice
Jasvis uses Windows text-to-speech voices via `pyttsx3`. Install a Hindi voice in Windows Settings > Time & language > Language & region if one is not available. If no Hindi voice is installed, replies may be spoken with the default system voice.

## Important limitations
- Voice recognition uses Google's online speech service; it is not fully offline.
- The wake word is not always-on in this starter version. Click Voice before each command.
- Opening a website is limited to launching a browser URL; it does not control arbitrary website actions.
- Chat memory is local conversation history used as context for the next AI request, not permanent human-like memory.
- Never hard-code or publish API keys.
