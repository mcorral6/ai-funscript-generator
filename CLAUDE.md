\# AI Funscript Generator - Claude Code Instructions



\## Project Overview



This project is an AI-assisted video analysis application that generates synchronized `.funscript` files from video input.



The goal is to create a modular, maintainable application that can:



1\. Accept video input.

2\. Analyze motion using computer vision.

3\. Convert detected motion into a normalized motion signal.

4\. Generate a valid `.funscript` JSON file.

5\. Provide tools for reviewing and improving generated scripts.



\---



\# Development Philosophy



Build incrementally.



Do not attempt to create the entire application at once.



Every feature should:

\- Have a clear purpose.

\- Be implemented as a separate module.

\- Include testing where practical.

\- Be documented.



Prefer reliability and transparency over black-box solutions.



\---



\# Technology Stack



Primary language:



\- Python 3.11+



Core libraries:



\- OpenCV

\- MediaPipe

\- NumPy

\- SciPy

\- FFmpeg

\- PySide6 (desktop interface)



Development tools:



\- Git

\- pytest

\- virtual environments



\---



\# Planned Architecture



The application should be separated into these layers:



\## Video Layer



Responsible for:

\- Loading video files.

\- Extracting frames.

\- Managing timestamps.

\- Handling codecs.



\## Detection Layer



Responsible for:

\- Motion detection.

\- Pose estimation.

\- Tracking.

\- Feature extraction.



\## Processing Layer



Responsible for:

\- Filtering.

\- Smoothing.

\- Normalization.

\- Signal generation.



\## Export Layer



Responsible for:

\- Creating `.funscript` files.

\- Validating output.



\## UI Layer



Responsible for:

\- User interaction.

\- Progress display.

\- Preview tools.



\---



\# Coding Standards



Follow these rules:



\- Write clean Python.

\- Use type hints.

\- Keep functions small.

\- Add docstrings to public functions.

\- Avoid unnecessary dependencies.

\- Prefer readable code over clever code.



\---



\# Development Order



Implement in this order:



1\. Project structure.

2\. Video loading.

3\. Frame extraction.

4\. Motion analysis.

5\. Signal processing.

6\. `.funscript` export.

7\. Visualization.

8\. Desktop interface.

9\. Advanced AI features.



\---



\# Important Rule



Do not replace working components with new approaches unless there is a measurable improvement.



Preserve modularity so algorithms can be swapped later.

