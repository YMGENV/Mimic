# Mimic 1.2 test results

- Required app files present: PASS
- JavaScript syntax (`node --check app.js`): PASS
- Real browser camera and photo/video capture: NOT RUN in this environment
- Physical folder writing with File System Access API: NOT RUN in a real browser
- Speech synthesis: NOT RUN in a real browser
- Speech recognition and “Hey Mimic” wake phrase: NOT RUN in a real browser

Known limitations:
- This version has a local conversational response engine, not a full generative AI model.
- Web Speech recognition is browser-dependent and may stop in background tabs, require internet, or be unavailable. This is not a guaranteed OS-level always-on wake word.
- The selected folder handle is held for the current page session; choose the folder again after reopening.
- Files are written to the selected folder's top level; the app does not create Photos/Videos subfolders.
- Removing items from the gallery does not delete physical files already written to the selected folder.
