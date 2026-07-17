# \# AI Funscript Generator

# 

# An AI-assisted computer vision application for analyzing video motion and generating synchronized `.funscript` files.

# 

# \---

# 

# \# Overview

# 

# AI Funscript Generator is a modular video analysis system designed to:

# 

# \- Import video files.

# \- Analyze movement using computer vision.

# \- Extract motion signals.

# \- Process and optimize motion data.

# \- Export synchronized `.funscript` files.

# 

# The project is designed to be transparent, testable, and extensible.

# 

# \---

# 

# \# Project Goals

# 

# The long-term vision is a desktop application where a user can:

# 

# 1\. Select a video file.

# 2\. Run automated motion analysis.

# 3\. Review the generated motion curve.

# 4\. Export a `.funscript` file.

# 

# \---

# 

# \# Technology Stack

# 

# \## Language

# 

# \- Python 3.11+

# 

# \## Computer Vision

# 

# \- OpenCV

# \- MediaPipe

# \- FFmpeg

# 

# \## Data Processing

# 

# \- NumPy

# \- SciPy

# 

# \## User Interface

# 

# \- PySide6

# 

# \## Development

# 

# \- Git

# \- pytest

# 

# \---

# 

# \# Project Structure

# ai-funscript-generator/

# 

# ├── CLAUDE.md

# ├── PROJECT\_SPEC.md

# ├── ARCHITECTURE.md

# ├── TASKS.md

# ├── README.md

# │

# ├── src/

# │ ├── video/

# │ ├── detection/

# │ ├── processing/

# │ ├── export/

# │ └── ui/

# │

# ├── tests/

# ├── models/

# ├── samples/

# ├── output/

# │

# └── requirements.txt



\---



\# Development Status



Current status:





Documentation Complete

Implementation Starting





\---



\# Installation



\## Clone Repository



```bash

git clone https://github.com/mcorral6/ai-funscript-generator.git



cd ai-funscript-generator

Create Virtual Environment



Windows:



python -m venv venv



venv\\Scripts\\activate



macOS/Linux:



python3 -m venv venv



source venv/bin/activate

Install Dependencies

pip install -r requirements.txt

Running the Application



The first version will use a command line interface.



Example:



python src/main.py video.mp4



Future versions will provide a desktop application.



Development Roadmap

Phase 1



Project foundation.



Status:



In Progress

Phase 2



Video processing.



Goal:



Read video files and extract frames.



Phase 3



Motion detection.



Goal:



Extract movement information.



Phase 4



Signal processing.



Goal:



Convert raw motion into a clean signal.



Phase 5



Funscript export.



Goal:



Generate valid output files.



Phase 6



Desktop interface.



Goal:



Create a complete user application.



Contributing



Development should follow the project documentation.



Before adding features:



Review PROJECT\_SPEC.md.

Review ARCHITECTURE.md.

Update TASKS.md.

License



To be determined.



