# Mimic 1.2

Mimic 1.2 builds on the original browser camera assistant with a friendlier chat experience, spoken replies, one-shot voice input, and an optional **“Hey Mimic”** wake-phrase listener.

## Run locally
1. Extract this ZIP.
2. Open a terminal in the `Mimic-main` folder.
3. Run `python -m http.server 8000` (or another local HTTP server).
4. Open `http://localhost:8000` in desktop Chrome or Edge.
5. Click **Enable camera** and grant camera/microphone permissions when asked.
6. Click **Enable “Hey Mimic”** and grant microphone permission to try the wake phrase.

Camera and microphone APIs require a secure context; `localhost` qualifies. On GitHub Pages, use the HTTPS site. Browser support varies by device.

## Voice behavior
- **Speak once** listens for one spoken command or message.
- **Hey Mimic** keeps browser speech recognition running where supported. Say “Hey Mimic, take a photo” or “Hey Mimic” followed by your command.
- After hearing only the wake phrase, Mimic waits briefly for the next phrase.
- Browser speech recognition may stop in background tabs, require internet, or be unavailable. It is not equivalent to an operating-system always-on wake-word service. Keep the page open and awake for best results.
- Spoken replies can be switched off in Voice & privacy.

## Chat capability
This version includes a local conversational response engine for greetings, small talk, help, time/date, jokes, and a few common conversational topics. It does **not** connect to a full generative AI model yet. Open-ended, ChatGPT-like conversations require a server-side AI backend; do not place private provider API keys in front-end JavaScript or a public GitHub Pages repository.

## Camera and storage
- `take a picture`
- `record a 15 second video` (or another duration up to 300 seconds)
- `stop recording`
- `show gallery`
- `choose save folder`

After a folder is chosen, new media is written to its top level and also kept in IndexedDB. Folder access is supported mainly in recent desktop Chrome/Edge; on other browsers, use the browser gallery and download links. The app asks for camera/microphone permission only when you start those features.

## Tests and limitations
See `TEST-RESULTS.md`. Syntax and static file checks can be run locally with `node --check app.js`. Camera capture, folder writes, speech synthesis, and the wake phrase should be tested on the actual target browser/device.
