# Kinematic Parking Simulator

An interactive, single-file **HTML5 parking simulator** for teaching and experimenting with vehicle path planning, parking maneuvers, and basic autonomous driving concepts.

> **Developed by Dr. Vahid Tavakkoli for educational purpose.**

---

## Overview

This project demonstrates how a kinematic vehicle can:

- Enter parking bays using **forward** or **reverse** motion,
- Handle different parking lot geometries,
- Follow editable user-defined trajectories,
- Evaluate collision and feasibility constraints,
- Optionally include a **trailer** for advanced maneuvering behavior.

The simulator is implemented in a single `index.html` file using plain JavaScript, HTML, and CSS (no external dependencies).

---

## Main Features

- **Parking Schemes**
  - Parallel parking
  - Perpendicular parking
  - Angled parking

- **Direction Modes**
  - Reverse (by tail)
  - Forward (by head)

- **Interactive Path Editing**
  - Toggle path edit mode
  - Drag control points
  - Add and delete points
  - Re-simulate quickly from updated control geometry

- **Simulation Controls**
  - Simulate path
  - Start / Pause / Reset animation
  - Target bay selection

- **Safety and Validation**
  - Collision-aware footprint checking
  - Feasibility status feedback
  - Dashed preview trace of tracked trajectory

- **Scenario Persistence**
  - Save scenarios in browser storage
  - Load and delete saved scenarios
  - Export and import scenarios as JSON

- **Trailer Support**
  - Optional trailer dynamics for more advanced educational demonstrations

---

## Educational Value

This simulator can be used in courses, labs, and demonstrations related to:

- Vehicle kinematics,
- Motion planning,
- Trajectory tracking,
- Collision detection,
- Human-in-the-loop path design.

Because all logic is visible in one file, students can directly inspect and modify the algorithms.

---

## Quick Start

1. Clone or download this repository.
2. Open `index.html` in any modern browser.
3. Choose scheme, direction, and target bay.
4. Click **Simulate Path**, then **Start**.
5. Optionally enable **Edit path** and tune control points.

No build tools or package installation are required.

---

## Project Structure

```text
.
├── index.html   # Full simulator (UI + rendering + kinematics + persistence)
└── README.md
```

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgment

Created and maintained for educational use by **Dr. Vahid Tavakkoli**.
