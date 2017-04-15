
Included in this submission is the final body of source code that comprises the software component of ’Vision-Based 3D Trajectory Analysis for Grassroots Football’. The software has been affectionately and unofficially dubbed ‘squawkFly’.

Not included in this submission are *all* of the resources (multimedia, libraries and dependencies) to build and run the program out of the box. The captured data used during development is either in video format (mp4 or mkv) or stored additionally as an image sequence (png), which runs the resources directory into several GB of disk space.

Instead, res/ contains just enough resources to carry out a single run of the software once the relevant dependencies are installed.

————————————————————————————————————————

A simple demo/screen-capture of the software is uploaded along with the code.

————————————————————————————————————————

All of the source files should have a multi-line header comment explaining they’re general purpose, and where they fit into the overall system.

Dependencies:
	- Python 2.7.x
	- OpenCV 2.4.11
	- X3DOM  1.7.0

Python packages:
	- Yattag 1.5.0
	- Numpy 1.9.2
	- Matplotlib 1.4.3

Navigating the submission:

- src/ contains all of the final source code. The most important scripts are:
	- squawkFly.py (GUI and flow control)
	- detect.py (Ball candidate detection)
	- kalman.py (Trajectory segmentation)
	- trajectories.py (Trajectory Selection)
	- interpolate.py (Trajectory Interpolation)
	- reconstruct.py (3D reconstruction)
	- generate_x3d.py (3D XHTML Model Generation)

- res/ contains four videos that can be used to demo the software:
	- camera1_calibration.MOV
	- camera2_calibration/
	- camera1_freekick.mkv
	- camera2_freekick.mp4

- data/ contains various text files used throughout the softwares runtime. There’s no real need to look at these, they simply provide a place for each pipeline stage to read and write it’s results.

- sessions/ contains the session and clip data that the main program will read and write. Inside each session are a series of clips. Inside each clip is the data specific to that clip like trajectory detections. A single session: ‘demo’ has been submitted.

RUNNING IT:

If you happen to have all the dependencies installed, you can try watching the software in action by running ./squawkfly.py and just hitting ANALYSE. The input fields have already been populated with relative paths to the demo resources, so excluding cross-platform mishaps (I developed on OS X) it should run happily. This should create a new clip called demo_clip inside the ‘demo’ session, within /sessions.
