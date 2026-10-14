# Mimic

A small browser-based personal camera assistant with explicit camera access, still photos, timed videos, text/voice commands, and a gallery.

## Run locally
1. Extract the ZIP.
2. Open a terminal in the `Mimic` folder.
3. Run `python -m http.server 8000` (or another local HTTP server).
4. Open `http://localhost:8000` in desktop Chrome or Edge.
5. Click **Choose save folder** and select the folder you created for Mimic. Grant access when prompted.
6. Click **Enable camera** and grant camera/microphone permissions.

Camera APIs require a secure context; `localhost` qualifies. The folder picker generally requires a supported desktop browser and a user gesture. On browsers without the File System Access API, the app falls back to IndexedDB plus download/export links.

## Commands
- `take a picture`
- `record a 15 second video`
- `record a 30 second video`
- `stop recording`
- `show gallery`
- `choose save folder`

## Storage behavior
After a folder is chosen, new media is written to the selected folder's top level and also kept in the browser's IndexedDB gallery. The app does not create `Photos` and `Videos` subfolders automatically in this version. Removing an item from the gallery does not delete the physical file in the selected folder.

## Limitations
- Browser camera, microphone, video encoding, and speech recognition depend on device/browser support and user permissions.
- Folder handles are held for the current page session; choose the folder again after reopening if necessary.
- Voice recognition uses browser speech recognition and may be unavailable or require internet depending on browser.
