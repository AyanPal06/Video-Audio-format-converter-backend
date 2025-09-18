Internship Assignment - Final Submission Package
Deadline: September 12, 2025 23:59

This package contains two Flask APIs:
- video_converter/  (runs on port 5001)
- audio_converter/  (runs on port 5002)

Each app uses ffmpeg to perform conversions. ffmpeg is **required** on the host machine.

How to run (example for Linux / WSL / macOS):
1. Install ffmpeg (instructions depend on OS). Example on Ubuntu:
   sudo apt update
   sudo apt install ffmpeg python3-venv

2. For each service:
   cd video_converter
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   python app.py

   (Repeat for audio_converter)

3. Use the `/convert` endpoint as documented in docs/*.md

What is included in this file:
- video_converter/app.py
- video_converter/requirements.txt
- audio_converter/app.py
- audio_converter/requirements.txt
- docs/video_api_doc.md
- docs/audio_api_doc.md
- this README

Limitations & Notes:
- The APIs save uploaded files temporarily in `uploads/` folder inside the app directory. Remove old files periodically.