# Task_06_LLM_Video_Generation

# Task_06_LLM_Video_Interview

Short, street-style AI video interview generated with an LLM video tool (e.g., Google Flow, D-ID, HeyGen, Runway), then stitched locally.

## What’s here

- `prompts/` – ready-to-use prompts for 3 short clips (≈8s each).
- `scripts/stitch.py` – tiny MoviePy script to concatenate clips.
- `media/` – put your local MP4s here (ignored by default to avoid large binaries).
- `requirements.txt` – Python deps for stitching.
- `.gitignore` – ignores large media by default.

## Reproduce

1. Generate each clip with your video tool of choice:
   - Use `prompts/clip1.txt`, `prompts/clip2.txt`, `prompts/clip3.txt`.
   - **Important:** do not use real names/likeness of prominent people. Use a generic role (e.g., “a young Syracuse guard”).
   - Export MP4s and place them in `media/` as `clip1.mp4`, `clip2.mp4`, `clip3.mp4`.

2. (Optional) Stitch the clips:
   ```bash
   python -m venv .venv
   .venv/Scripts/activate        # Windows
   # source .venv/bin/activate   # Mac/Linux

   pip install -r requirements.txt
   # Ensure FFmpeg is installed (Windows: choco install ffmpeg, Mac: brew install ffmpeg)

   python scripts/stitch.py --clips media/clip1.mp4 media/clip2.mp4 media/clip3.mp4 --out media/final_interview.mp4
