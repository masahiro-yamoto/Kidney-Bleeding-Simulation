# Kidney-Bleeding-Simulation

Unity-based kidney bleeding simulation using Obi Fluid.

This project simulates a depth-responsive kidney bleeding model
for educational and minimally invasive surgical training research.

---

## Purpose

To develop a structured and reproducible bleeding severity model
for surgical education and procedural simulation research.

The system aims to provide:

* Visual comparison of bleeding severity levels
* Controlled parameter reproducibility
* Spatial incision-based activation
* Depth-dependent bleeding response
* Vessel-aware bleeding simulation based on surface vascular mapping

---

## Simulation Architecture

The bleeding system is organized into three predefined severity levels.

### Level1 – Mild Baseline (Venous-like)

Stable mild continuous bleeding.
Minimal pooling.
Non-pulsatile behavior.

### Level2 – Moderate Continuous Model

Increased flow intensity compared to Level1.
Higher particle velocity and pooling behavior.
Non-pulsatile configuration maintained for controlled comparison.

### Level3 – Arterial Pulsatile Model

Depth-responsive pulsatile bleeding using scripted modulation.
Simulates arterial pressure wave behavior.
Slightly exaggerated for educational visualization clarity.

Each level uses independently configured emitters
to preserve parameter stability and reproducibility.

---

## Depth-Based Incision Model (v0.5)

A raycast-driven incision model dynamically calculates incision depth:

* Initial surface contact point stored as reference
* Surface normal recorded for depth vector calculation
* Real-time depth computed using vector dot product
* Bleeding intensity scaled proportionally to incision depth

Bleeding characteristics include:

* Normal-direction offset positioning (prevents internal particle emergence)
* Surface-aligned emission vector
* Continuous (non-stepwise) intensity scaling
* Optional sinusoidal modulation for arterial pulse simulation

This enables realistic depth-dependent bleeding behavior.


---

## Vessel Texture-Based Vascular Injury Model (v0.9)

A vessel-aware bleeding model was implemented using UV texture mapping.

Instead of explicit vessel mesh construction,
vascular distribution is represented by a grayscale vessel map texture.

Workflow:

* UV unwrapping performed in Blender
* Vessel distribution manually painted on UV map
* Texture imported into Unity
* Runtime vessel detection via raycast UV sampling

Bleeding occurs only when incision intersects vessel regions.

Additional features:

* Vessel persistence after injury
* Dynamic bleeding source relocation
* Vessel-thickness dependent bleeding intensity
* Surface-guided blood flow simulation

This enables simplified vascular injury simulation
without complex anatomical vessel modeling.

---

## Interaction Model

The simulator includes raycast-based surgical interaction:

* `Camera.main` automatic camera reference
* `ScreenPointToRay` for 2D-to-3D interaction mapping
* `Physics.Raycast` for kidney collider detection
* Tag-based filtering for organ-specific interaction

This allows bleeding activation and modulation
through simulated incision input.

---

## Fluid Behavior Configuration

Key physical parameters:

* Tuned viscosity for realistic blood-like flow behavior
* Solver substeps increased to reduce particle tunneling
* Collision iterations adjusted for surface adherence
* Surface offset correction to prevent mesh penetration

These adjustments significantly improved visual plausibility
and reduced internal particle artifacts.

---

## Current Status

* Kidney model integrated
* Three-level bleeding architecture established
* Raycast-based incision activation completed
* Depth-dependent bleeding scaling implemented
* Pulsatile arterial modulation added
* Surface penetration mitigation configured
* Fixed bleeding source position implemented
* Real-time bleeding UI integrated
* CSV logging for quantitative analysis
* Vessel texture-based bleeding model implemented
* Surface-flow blood simulation added
* Persistent vascular injury state implemented
* Parameter documentation structured

---

## Future Work

* UI-based severity switching
* Hemostasis interaction modeling
* True mesh incision visualization
* Pressure-responsive bleeding adaptation
* Robotic manipulation system integration
* Quantitative evaluation metrics for training validation
*  Dynamic blood stain accumulation
* Emergency conversion scenario
* Multi-vessel bleeding
* Internal vascular structure modeling

---

## Development Progress

* v0.1: Constant bleeding simulation
* v0.2: Multi-level bleeding structure
* v0.3: Raycast-based incision activation
* v0.4: Pulsatile arterial model
* v0.5: Depth-responsive bleeding model with surface stabilization
* v0.6: Hemostasis interaction
* v0.7: UI + CSV quantitative analysis
* v0.8: Fixed bleeding source
* v0.9: Vessel texture-based vascular injury model

---

## Screenshots

![simulation](screenshots_simulation_20260303.png)
![simulation](BleedingIntensityResponseToIncisionDepthandHemosasis.png)

## Vessel Map

![simulation](vessel_map.png)

## Demo

[![Kidney Bleeding Simulation Demo](https://img.youtube.com/vi/n4kzwEsFI_s/0.jpg)](https://youtube.com/shorts/n4kzwEsFI_s?feature=share)

This demo shows depth-dependent bleeding and coagulation interaction.

## Key Features

- Depth-based bleeding response
- Vessel-aware bleeding activation
- Surface vascular mapping
- Persistent vessel injury state
- Surface blood flow simulation
- Coagulation (hemostasis) interaction
- Real-time bleeding visualization
- CSV-based quantitative logging

## Result
- Bleeding intensity increases with depth
- Coagulation reduces bleeding over time

