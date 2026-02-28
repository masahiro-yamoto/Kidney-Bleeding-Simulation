# Development Log

## 2026-02-24
- Imported Kidney 3D model
- Implemented constant bleeding using Obi Fluid
- Adjusted emitter speed（1.2）

Problems:
- Particle penetraion observed at high speed

Next:
- Add multi-level bleeding control

---

## 2026-02-27
- Implemented 3-level bleeding control(Level 1-3)
- Successfully adjusted emitter speed via key input
- Created repository
- Add README

## 2026-02-28

### Level1 Baseline (Mild bleeding)

Speed: 0.25  
Lifespan: 4  
Disk Radius: 0.5  

This configuration is defined as the baseline for quantitative comparison.

### Level1 Baseline Visualization

![Level1 Baseline](level1_baseline_20260228.png)

Observation:
- Stable flow
- Moderate pooling on surface
- No excessive spray
