# GRC XploreBot AI Planner

AI-assisted mission planning for the XploreBot GRC Engineers Game.

## Flow

Mission document + competition mat image -> NVIDIA vision model -> structured route -> route validation -> ai_mission.py -> XploreBot MicroPython controller.

The AI plans the route. The robot firmware remains responsible for real-time IR sensing, PID line following, 90-degree turns, and motor control.

## Setup

Requirements: Python 3.10+, NVIDIA API key, mission guide PDF/TXT/MD, and a photo of the GRC competition mat.

Install:

    pip install -r requirements.txt

Create `.env` from `.env.example` and add your NVIDIA API key. Never commit `.env`.

Place `mission_guide.pdf` and `grc_mat.jpg` in the project directory, then run:

    python planner.py

The planner generates `ai_mission.py`. Copy that file to the XploreBot MicroPython project.

Route commands: S = straight, L = 90-degree left, R = 90-degree right, X = stop/mission complete.

The mission document should contain the official rules and instructions. The mat image should clearly show the competition layout.
