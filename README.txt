YOLOv11 Object Detector — Standalone
======================================

Files in this folder:
  index.html          — the detector app (open this)
  yolo11n.onnx        — YOLOv11n model (download separately, see below)
  download_model.py   — helper script to download the model
  README.txt          — this file


QUICK START
-----------

Step 1 — Download the model (one time only):

    python download_model.py

  Or open index.html and click "Download model automatically"
  (requires an internet connection for the first run).

Step 2 — Open the app:

  Option A (easiest, Chrome/Edge):
    Double-click index.html

    On first run, click "Select yolo11n.onnx" and pick the model file.
    The app caches it in your browser — future opens load instantly with no internet.

  Option B (best compatibility, all browsers):
    Run a local HTTP server in this folder:
        python -m http.server 8080
    Then open: http://localhost:8080

    The app will find yolo11n.onnx automatically.


HOW IT WORKS
------------
- Model is run entirely in your browser via ONNX Runtime WebAssembly.
- After the first load, the model is stored in IndexedDB and loads offline.
- No data leaves your computer.
- Works with any webcam; use the Camera dropdown to switch between them.


REQUIREMENTS
------------
- Modern browser: Chrome 90+, Edge 90+, Firefox 90+, Safari 16+
- Webcam
- Internet connection (for ONNX Runtime WASM from CDN — first run only)
- ~10 MB disk space for the model file


TIPS
----
- If nothing is detected, try moving closer to the camera or improving lighting.
- The model detects 80 object types (COCO dataset): people, cars, animals, etc.
- Detection threshold is 25% confidence — objects below this are ignored.
