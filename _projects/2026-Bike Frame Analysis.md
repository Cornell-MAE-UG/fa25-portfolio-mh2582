---
layout: project
title: Bike Frame Design Project
description: MAE 3150 Final Project (FEA & Structural Analysis)
technologies: Autodesk Fusion360, ANSYS
image: /assets/images/bike frame.png
---

Structural analysis and optimization of an electric bike frame for a bike share program, using finite element analysis in ANSYS to evaluate deformation, stress, and factor of safety across two frame designs.

## Table of Contents
- [Overview](#overview)
- [Initial Geometry Analysis](#initial-geometry-analysis)
- [New Design](#new-design)
- [Optimization](#optimization)

---

## Overview {#overview}

The goal of this project was to design and analyze a bicycle frame suitable for a wide-deployment electric bike share program — one that is lightweight, safe, durable, and inexpensive. Bikes in such programs provide accessible transportation for communities and college campuses, reducing dependence on cars while promoting physical activity.

Two frame designs were modeled in Fusion 360 and analyzed in ANSYS using shell theory with SHELL181 elements. The structure was meshed and evaluated under realistic loading conditions: a 150 N seat force and a 700 N pedal force, with fixed supports at the head tube and rear frame corners. The target factor of safety for all components was at least 2. The chosen material for both models was aluminum alloy.

---

## Initial Geometry Analysis {#initial-geometry-analysis}

The initial frame followed a standard bicycle geometry with seat, top, down, and head tubes of 35 mm diameter and chain and seat stays of 15 mm diameter. A wall thickness of 2 mm and element size of 4 mm were used.

**Results:**
- **Total deformation:** Maximum of 0.0772 mm, concentrated at the seat tube and bottom bracket where the seat and pedal forces are applied. Deformation decreases toward the fixed supports, which is physically consistent.
- **Von-Mises stress:** Maximum of 26.917 MPa at the bottom bracket, driven by the convergence of adjacent tubes and the high pedal load. The majority of the structure experienced very low stress.
- **Factor of safety:** Minimum of 10.402 — well above the target of 2, confirming the initial design is structurally safe under the given loading conditions.

**Verification:** Reducing the element size from 4 mm to 3 mm produced identical deformation and safety factor results, with a small increase in stress consistent with improved mesh precision. This confirms the original results are reliable.

---

## New Design {#new-design}

The new design was modified with accessibility and electric bike functionality in mind:

- **Top tube removed** to lower the step-over height, making the bike easier to mount for a wider range of users.
- **Head tube moved closer to the seat tube**, reducing the distance from 582.734 mm to 553.372 mm to shorten the moment arm from handlebar forces.
- **Seat and down tube diameters increased** from 35 mm to 40 mm to increase the moment of inertia and reduce stress at the bottom bracket.
- **Battery load added** — a 30 N distributed load applied along 300 mm of the down tube to simulate the weight of the electric battery.

**Results:**
- **Total deformation:** Maximum of 0.1272 mm near the seat load application point — higher than the initial design due to the added battery load and geometry changes.
- **Von-Mises stress:** Maximum of 54.246 MPa at the bottom bracket. The increase relative to the initial geometry is expected, as the battery weight acts in the same direction as the seat and pedal loads.
- **Factor of safety:** Minimum of 5.162 — still well above the target of 2, confirming the modified design remains structurally safe.

**Verification:** Refining the mesh to 3 mm again produced consistent deformation and safety factor results, with a slight stress increase as expected. The model is confirmed reasonable.

---

## Optimization {#optimization}

To minimize material use while maintaining structural safety, a parametric response surface optimization was performed on the seat and down tube wall thicknesses, the two tubes whose diameters were changed in the new design. The allowable thickness range was set to 2–4 mm, with candidate points evaluated at equal thickness pairs (2 mm, 3 mm, and 4 mm).

**Results:**
- Seat tube average mass: ~0.292 kg (negligible variation across the range)
- Down tube average mass: ~0.5541 kg
- Minimum factor of safety across all candidates: 5.1625 — still well above the threshold of 2

The optimization confirmed that the frame has significant structural margin across the full thickness range tested, meaning lighter wall thicknesses could be used without compromising safety. This supports the goal of reducing material cost and weight for a practical bike share deployment.

[View Full Project Report]({{ "assets/MAE 3150 Bike Frame Project Report.pdf" | relative_url }})
