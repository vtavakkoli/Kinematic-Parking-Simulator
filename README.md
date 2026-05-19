# 🚗 Interactive Parking Path Planner & Simulator

A **100% working, zero-dependency, single-file HTML5 application** that simulates autonomous vehicle path planning, tracking, and parking. This simulator includes support for complex scenarios like reverse parking, angled parking, and even navigating with an attached trailer.

## ✨ Key Features

* **Interactive Path Editing**: Uses a "Sparse Editable Control Points" system. Users can drag, drop, add, or delete key points on the path while the simulator recalculates the actual driving trace in real-time.
* **Multiple Parking Schemes**: Test parallel, perpendicular, and angled parking schemes.
* **Forward & Reverse Kinematics**: Accurately simulates the steering logic required to back a vehicle (and trailer) into a tight spot.
* **Trailer Dynamics**: Toggle a trailer hitch! The simulator calculates advanced hitch angles and trailer sweep/footprints.
* **Collision Detection**: Real-time safety footprint checks. If the vehicle or trailer clips a parking bay or a boundary wall, the simulation pauses and reports the collision.
* **Save/Load Scenarios**: Export your customized, feasible parking paths as JSON files or save them directly in your browser's local storage.
* **Feasibility Checking**: Automatically sweeps the path before running to ensure the physics and kinematics of the car can actually make the turns without crashing.

## 🛠️ How It Works (Under the Hood)

This simulator relies on several advanced concepts from robotics, autonomous driving, and computer graphics:

1. **Kinematic Bicycle Model**: The car's movement is simulated using a standard mathematical model for vehicles. It calculates X/Y position, Yaw (heading), Velocity, and Steering Angle over small time steps (`dt`).
2. **Trailer Math**: When the trailer is enabled, the code tracks a secondary `trailerYaw`. As the car reverses, the steering controller mathematically pushes the trailer to prevent jackknifing, using relative hitch angles.
3. **Path Generation (Catmull-Rom & Bezier)**: 
    * When generating an auto-path, it uses cubic Bezier curves to smoothly connect the starting point, staging area, and target parking bay.
    * When you manually edit the path, it uses **Catmull-Rom Splines** to ensure the dense tracking path smoothly passes through every single control point you placed.
4. **Pure Pursuit Path Tracking**: The vehicle follows the generated path using a look-ahead controller (similar to "Pure Pursuit"). It finds a point slightly ahead on the path and calculates the required steering angle to intercept it.
5. **Separating Axis Theorem (SAT)**: Collision detection is handled by projecting the corners of the vehicle (and trailer) polygons against the parking bay polygons. If the shapes intersect, a crash is registered.

## 🚀 Getting Started

Because this project is built with vanilla HTML, CSS, and JavaScript, there is no build step required!

1. Clone the repository:
   ```bash
   git clone https://github.com/YourUsername/AutoPark-Sim.git
