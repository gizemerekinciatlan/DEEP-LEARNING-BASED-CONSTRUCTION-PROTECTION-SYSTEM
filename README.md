# Deep Learning-Based Construction Protection System

## Overview
A construction site safety system that uses YOLOv5 and computer vision to detect the distance between workers and heavy machinery, sending real-time warnings when a worker gets too close. A Vue.js-based management portal displays and manages these warnings.

## Repository Structure
- `yolov5/` — customized YOLOv5 scripts (`detect.py`, `train.py`, `export.py`) for worker–machinery distance detection
- `my_project/` — Vue.js warning management portal

## Setup & Usage

1. Clone this repository and open the folder with any code editor.
2. Open a terminal and run: `cd yolov5`
3. Install requirements: `pip install -r requirements.txt`
4. Open `detect.py`. Around line 222, the camera source default is set to `'1'` (external camera). To use your local/built-in camera instead, change it to `'0'`.
5. Run `detect.py` — target detection is now active.
6. Reopen the terminal and run: `cd my_project`
7. Install dependencies: `npm install`
8. After installation, run: `npm run serve`
9. Click the link shown in the terminal to open the web page.

## Acknowledgements
This project was developed together with **Yuchen Deng** as part of the Design Driven Project (DDP) course, RWTH Aachen.
