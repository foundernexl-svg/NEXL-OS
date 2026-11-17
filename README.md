# NEXL-OS
The Windows for Warehouse Robots - An operating layer for multi-robot intelligence

### 🚀 Live Demo: https://LarryRonex.github.io/NEXL-OS/

### 🔥 v0.2 Update: My robots now understand S, M, L sizes
- Payload-based allocation (S/M/L)
- Tested by 4 operators
- Bug fixes + Avg delivery time 13s
- Built from Jatara, MP

## What is NEXL-OS?
NEXL-OS is a self-healing operating system for warehouse robots. Unlike simple grid demos, it solves real-world problems like deadlocks, collisions, and humans walking into aisles.

## Core Tech Inside (v0.2)
**1. Space-Time A* Routing:**
Robots plan in (x, y, time). Waiting is an action. They queue instead of colliding.

**2. Deadlock Detection & Auto-Yield:**
- Detects head-on swaps and same-tile conflicts 80 steps ahead
- Lower priority robot auto-yields: `R2 yields to R1`
- Auto re-plans: `replan()`

**3. Self-Healing Escape:**
If stuck > 2.5s, robot steps aside: `stuck for 2.5s, escape maneuver: stepping aside`

**4. Real Warehouse Logic:**
- One-way lanes (like Amazon Kiva)
- Perception layer: `R1 sees a person, re-planning`
- Heavy load = slower move: `task.kg>25?2:1`
- Battery + Auto-charging docks
- Emergency Stop

**5. NEW in v0.2 - Payload Logic:**
- Size-aware: `task.size=S/M/L`
- Smarter allocation based on size

## How to Use
- **Click on floor:** Place / Remove wall - robots auto re-route
- **New task:** Assign pick & drop
- **Drop person:** Test human obstacle avoidance
- **Heatmap:** See most used paths
- **E-stop:** Halt all robots

## Tech Stack
Single file `index.html` - Vanilla JS, Isometric Engine, No dependencies. Runs on any phone.

## Vision
To be the Android for logistics robots.
