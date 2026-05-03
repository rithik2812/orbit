# Orbital Guardian - Space Debris Collision Risk Simulator

## Overview

Orbital Guardian is an interactive simulation system designed to analyze satellite collision risk due to space debris.  
It provides a decision-support interface where users can modify orbital parameters and observe how risk levels change.

The system uses a physics-inspired heuristic model combined with real-time visualization.

---

## Features

- Interactive control of simulation parameters
  - Debris density
  - Orbital altitude
  - Satellite count
  - Relative velocity

- Real-time collision risk calculation
- Visual risk indicator (Low / Moderate / High)
- Dynamic simulation using HTML5 Canvas
- Lightweight and browser-based implementation

---

## System Architecture

```
User Input (Sliders)
        |
        v
Parameter Normalization
        |
        v
Risk Model (Weighted Formula)
        |
        v
Risk Score Calculation
        |
        v
Visualization + Output Display
```

---

## Risk Model

The system computes risk using a weighted formula:

```
Risk = 0.45 * debris_density
     + 0.25 * satellite_count
     + 0.20 * relative_velocity
     + 0.10 * inverse_altitude
```

### Normalization

- debris_density = debris / 50000
- satellite_count = satellites / 50
- relative_velocity = speed / 15
- inverse_altitude = 1 - min(1, altitude / 35786)

### Interpretation

- Lower altitude increases risk
- Higher debris density increases risk
- Higher relative velocity increases collision probability
- More satellites increase interaction chances

---

## Technology Stack

- HTML5
- CSS3
- JavaScript
- Canvas API (for visualization)

---

## How to Run

1. Clone the repository

```
git clone https://github.com/your-username/orbital-guardian.git
```

2. Open the project folder

```
cd orbital-guardian
```

3. Run the application

- Open `index.html` in a web browser

---

## Example Scenario

Input:

- Debris Density: 15000
- Altitude: 800 km
- Satellites: 8
- Speed: 7.8 km/s

Output:

- Risk Score: Moderate
- Visual representation of orbit and debris

---

## Limitations

- Uses heuristic (rule-based) model, not trained machine learning
- Simplified orbital mechanics
- No real-world satellite data integration
- Risk weights are manually defined

---

## Future Improvements

- Integrate real satellite and debris datasets
- Replace heuristic model with machine learning regression
- Improve physics accuracy (orbital mechanics)
- Add predictive analytics for collision avoidance
- Deploy as a web application

---

## Project Type

This project is a:

- Simulation system
- Decision-support tool
- Physics-inspired analytical model

