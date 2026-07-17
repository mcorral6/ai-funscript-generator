\# AI Funscript Generator - Architecture Document



\## 1. System Overview



The application is designed as a modular pipeline.



The complete flow is:



&#x20;            USER

&#x20;             |

&#x20;             v

&#x20;   +------------------+

&#x20;   | Video Interface  |

&#x20;   +------------------+

&#x20;             |

&#x20;             v

&#x20;   +------------------+

&#x20;   | Video Processor  |

&#x20;   +------------------+

&#x20;             |

&#x20;             v

&#x20;   +------------------+

&#x20;   | Motion Analysis  |

&#x20;   +------------------+

&#x20;             |

&#x20;             v

&#x20;   +------------------+

&#x20;   | Signal Processor |

&#x20;   +------------------+

&#x20;             |

&#x20;             v

&#x20;   +------------------+

&#x20;   | Funscript Export |

&#x20;   +------------------+

&#x20;             |

&#x20;             v

&#x20;         OUTPUT





Each stage should be independent and replaceable.



\---



\# 2. Repository Architecture



Recommended structure:



ai-funscript-generator/



├── CLAUDE.md

├── PROJECT\_SPEC.md

├── ARCHITECTURE.md

├── TASKS.md

├── README.md

│

├── src/

│ |

│ ├── main.py

│ |

│ ├── video/

│ │ ├── reader.py

│ │ ├── frames.py

│ │ └── metadata.py

│ |

│ ├── detection/

│ │ ├── pose.py

│ │ ├── optical\_flow.py

│ │ └── tracking.py

│ |

│ ├── processing/

│ │ ├── filtering.py

│ │ ├── normalize.py

│ │ └── compression.py

│ |

│ ├── export/

│ │ ├── funscript.py

│ │ └── validator.py

│ |

│ ├── ui/

│ │ └── application.py

│ |

│ └── config.py

│

├── tests/

│

├── models/

│

├── samples/

│

├── output/

│

├── requirements.txt

└── .gitignore





\---



\# 3. Module Responsibilities



\## Video Module



Location:

src/video/





Purpose:



Handle all video input.



Responsibilities:



\- Open files.

\- Read frames.

\- Extract metadata.

\- Provide timestamps.



Example interface:



```python

video = VideoReader("example.mp4")



for frame in video.frames():

&#x20;   process(frame)



Detection Module



Location:

src/detection/



Purpose:



Extract movement information.



Pose Detector



File:

pose.py





Purpose:



Use AI pose estimation.



Possible models:



MediaPipe

OpenPose



Output:



{

&#x20;"frame":100,

&#x20;"landmarks":\[

&#x20;   {

&#x20;     "name":"hip",

&#x20;     "x":0.5,

&#x20;     "y":0.6,

&#x20;     "confidence":0.98

&#x20;   }

&#x20;]

}



Optical Flow



File:

optical\_flow.py



Purpose:



Measure visual movement.



Output:

frame

motion magnitude

direction



Tracking



File:

tracking.py



Purpose:



Follow selected objects or regions.



Signal Processing Module



Location:

src/processing/



Purpose:



Convert raw motion into a clean signal.



Pipeline:

Raw Data



&#x20;   |

&#x20;   v



Noise Filtering



&#x20;   |

&#x20;   v



Normalization



&#x20;   |

&#x20;   v



Compression



&#x20;   |

&#x20;   v



Final Motion Curve



Filtering



Purpose:



Remove jitter.



Possible methods:



Gaussian filter.

Savitzky-Golay filter.

Moving average.



Normalization



Convert values into:

0-100



Example:

Before:

120

200

350



After:

0

45

100



Compression



Reduce unnecessary points.



Purpose:



Smaller files.

Smoother playback.

Easier editing.



Export Module



Location:

src/export/



Purpose:



Generate .funscript.



Responsibilities:



Create JSON.

Validate format.

Save output.



Interface:

export\_script(

&#x20;   timestamps,

&#x20;   positions,

&#x20;   filename

)



User Interface Module



Location:

src/ui/



Purpose:



Provide user interaction.



Initial features:



Select video.

Start analysis.

Display progress.

Export result.



Future features:



Video preview.

Motion graph.

Manual editing.



4\. Data Flow

Input

Video File



Example:

movie.mp4



Intermediate Data



Frame extraction:

frame\_number

timestamp

image



Motion extraction:

timestamp

motion\_value

confidence



Processed signal:

timestamp

position



Output

example.funscript



5\. Configuration



Settings should be centralized.



Example:

config.py



Possible settings:

VIDEO\_FPS = 30



SMOOTHING\_LEVEL = 0.5



MIN\_ACTION\_INTERVAL = 100



MODEL\_PATH = "./models/"



6\. Testing Strategy



Each module should have tests.



Examples:



Video Tests



Verify:



File loading.

Frame extraction.

Metadata.



Processing Tests



Verify:



Filtering.

Normalization.

Compression.



Export Tests



Verify:



JSON validity.

Required fields.

Correct ranges.



7\. Future Expansion



The architecture should allow:



Multiple AI Models



Example:

Pose Detector A

&#x20;      |

&#x20;      |

Pose Detector B

&#x20;      |

&#x20;      v

Motion Fusion



GPU Acceleration



Possible technologies:



CUDA.

Apple Metal.

TensorRT.



Cloud Processing



Future possibility:



Desktop Client



&#x20;     |



Cloud AI Server



&#x20;     |



Generated Script



8\. Design Principles



The architecture follows these principles:



Modular components.

Replaceable algorithms.

Clear data interfaces.

Testable code.

Human review capability.

Gradual improvement.







