---
wry: patch
---

On Windows, initialization scripts added with `for_main_frame_only: true` no longer run in subframes. WebView2 injects every document-created script into every frame, so each such script is now wrapped in `if (window.top === window) { ... }`. An embedded third-party frame no longer gets globals meant for the app page, matching macOS and Linux.
