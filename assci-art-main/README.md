# Video ASCII Player

This small Python script converts video frames into ASCII art and plays the video in your terminal.

Project files
- `video_ascii.py` - Main script that reads a video, converts frames to ASCII, and prints them to the terminal.
- `vid.mp4` - (example) a sample video file included in the repo root (if present).

Requirements
- Python 3.8+
- pip
- OpenCV for Python (`opencv-python`)
- NumPy (`numpy`)

Install dependencies

Open PowerShell and run:

```powershell
python -m pip install --upgrade pip
pip install opencv-python numpy
```

Usage

Run the script from the project root:

```powershell
python .\video_ascii.py
```

The script will prompt for:
- Path to the video file (e.g. `vid.mp4` or an absolute path).
- Terminal width (number of characters; default 80).
- FPS (frames per second). If you enter `0` the script will use the video's FPS when available.

Example interactive session

```text
Enter the path to the video file: vid.mp4
Enter terminal width (default 80): 100
Enter FPS (default: use video FPS): 0
```

Notes and tips
- The script clears the terminal on each frame. On Windows it uses `cls`, and on Unix it uses `clear`.
- If the video doesn't play, verify the path is correct and that OpenCV can open the file. Some video formats/codecs may require a system-level codec (or `ffmpeg` on your system).
- Increasing `width` produces finer detail but will be slower and may exceed your terminal height. The script scales height automatically to keep aspect ratio.
- If you want command-line arguments instead of interactive prompts, consider modifying `video_ascii.py` to accept `--path`, `--width`, and `--fps` using `argparse`.

Troubleshooting
- "Error: Video file '...' not found." — Ensure the file path is correct and you're running the script from the right working directory.
- "Could not open video" or blank output — Install `ffmpeg` or try converting the video to a more common codec (H.264 in an MP4 container).
- OpenCV install issues on Windows — Use a prebuilt wheel for your Python version, or try installing `opencv-python-headless` if you don't need GUI features.

License

This repository is provided as-is. Modify and reuse as you like.

Enjoy!
