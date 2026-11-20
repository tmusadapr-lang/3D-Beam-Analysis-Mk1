[3D Beam Analysis README.md](https://github.com/user-attachments/files/35133518/3D.Beam.Analysis.README.md)
# 3D Beam Analysis

**3D Beam Analysis** is an interactive, browser-based structural and mechanical engineering application for analyzing three-dimensional, stepped linear-elastic beams and shafts. Powered by a six-degree-of-freedom (6-DOF) direct stiffness finite element solver with exact analytical force reconstruction, it solves statically determinate and indeterminate 3D systems while providing real-time Three.js 3D rendering, cross-sectional stress maps and static failure checks.

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
  - [Beam, Material & Unit Controls](#beam-material--unit-controls)
  - [Stepped Cross-Section Library](#stepped-cross-section-library)
  - [Supports & 3D Loading Conditions](#supports--3d-loading-conditions)
  - [Interactive 3D Viewport, 2D Projections & Diagrams](#interactive-3d-viewport-2d-projections--diagrams)
  - [Cross-Sectional Stress & Failure Analysis](#cross-sectional-stress--failure-analysis)
  - [Verification, Reporting & UI Themes](#verification-reporting--ui-themes)
- [Workflow](#workflow)
- [Methodology & Accuracy](#methodology--accuracy)
- [Future Work](#future-work)
- [License](#license)

## Overview

Evaluating three-dimensional beams and stepped shafts often requires juggling hand calculations, spreadsheets, and heavyweight finite element packages. **3D Beam Analysis** bridges the gap between analytical mechanics and full 3D numerical simulation—solving arbitrary multi-axis support, stepped-section, and loading configurations in the browser while presenting interactive 3D visualizations, synchronized 2D projections, 3D internal force/deflection/twist diagrams, combined stress diagnostics, and automated `.docx` engineering reports.

## Key Features

### Beam, Material & Unit Controls

- **Geometry & Material Properties:** Configure total beam length, elastic modulus ($E$), shear modulus ($G$) / Poisson's ratio ($\nu$), yield and ultimate strengths ($S_y$, $S_{ut}$, $S_{uc}$), and material density ($\rho$).
- **Built-In Material Presets:** Quickly select from standard structural and shaft engineering alloys—including structural steels (S275, S355), medium-carbon and alloy shaft steels (EN8/080M40, hardened 4140), stainless steel 304, aluminium 6061-T6, and Class 30 grey cast iron—or define custom material properties.
- **Per-Field Unit Conversion:** Switch seamlessly between metric and imperial units on an individual per-field basis.
- **Preloaded 3D Examples:** Explore and modify built-in 3D example models covering multi-axis beam configurations and stepped shafts with gears and pulleys.

### Stepped Cross-Section Library

- **Multi-Step Beam Segments:** Define variable cross-sections along the longitudinal $x$-axis to model stepped shafts, segmented beams, and locally reinforced spans.
- **Standard & Custom Profiles:** Model solid rounds, round tubes, solid rectangles, rectangular hollow sections (RHS), I-sections, C-sections, or enter custom geometric properties ($A$, $I_y$, $I_z$, $J$) directly.
- **Live Dimensioned Preview:** View an automatically updated, dimensioned cross-section drawing alongside computed properties ($A$, $I_y$, $I_z$, $J$, $Z_y$, $Z_z$, $EI_y$, $EI_z$, and $GJ$).

### Supports & 3D Loading Conditions

- **6-DOF Boundary Conditions:** Place standard structural and mechanical support presets—**Pin**, **Roller**, **Journal Bearing**, **Thrust Bearing**, and **Fixed**—or configure custom degree-of-freedom restraints ($U_x, U_y, U_z, R_x, R_y, R_z$).
- **Comprehensive 3D Load Types:** Apply arbitrary 3D point forces ($F_x, F_y, F_z$), concentrated moments and torques ($M_x, M_y, M_z$), and uniform or trapezoidal distributed loads ($q_y, q_z$) anywhere along the span.
- **Automatic Self-Weight:** Toggle automatic gravitational self-weight loading ($\rho g A$) derived from each segment's cross-sectional area and material density.

### Interactive 3D Viewport, 2D Projections & Diagrams

- **Interactive 3D WebGL Scene (Three.js):** Inspect the stepped 3D beam geometry, scaled 3D load vectors, deflected-shape overlay, and procedural bearing hardware (sleeve pillow blocks, insert ball bearings, and roller supports) with smooth orbit, pan, and zoom controls.
- **Synchronized 2D Projections:** View live Elevation ($x\text{--}y$) and Plan ($x\text{--}z$) SVG schematics synchronized with the 3D model.
- **3D Internal Force, Deflection & Twist Diagrams:** Generate high-precision plots across every evaluated span station:
  - Shear Forces ($V_y(x)$, $V_z(x)$, and resultant $V(x)$)
  - Bending Moments ($M_y(x)$, $M_z(x)$, and resultant $M(x)$)
  - Slopes ($\theta_y(x)$, $\theta_z(x)$) & Lateral Deflections ($v(x)$, $w(x)$, and resultant $\delta(x)$)
  - Axial Force ($N(x)$) & Axial Displacement ($u(x)$)
  - Internal Torque ($T(x)$) & Angle of Twist ($\phi(x)$)

### Cross-Sectional Stress & Failure Analysis

- **2D Cross-Section Stress Distribution Maps:** Inspect combined normal stress ($\sigma_x = N/A - M_z y/I_z + M_y z/I_y$) and resultant shear stress ($\tau$ from transverse shear $VQ/Ib$ and torsional shear $T, J$) across any cross-section along the beam.
- **2D & 3D Stress State Visualization:** Examine 2D stress elements (standard orientation, principal stresses, and maximum in-plane shear) alongside an interactive 3D stress cube displaying ordered principal stresses ($\sigma_1 \ge \sigma_2 \ge \sigma_3$).
- **Multi-Theory Safety Factor Checks:** Evaluate governing structural safety factors across five classical static failure theories:
  1. von Mises (Distortion Energy)
  2. Tresca (Maximum Shear Stress)
  3. Maximum Normal Stress
  4. Coulomb-Mohr
  5. Modified Mohr

### Verification, Reporting & UI Themes

- **Benchmark Verification:** Compare 3D numerical solver outputs directly against closed-form textbook solutions.
- **Multi-Format Export:** Export individual plots and schematics as **SVG**, **PNG**, or **JPEG** files.
- **Automated Word Reports:** Generate a formatted Microsoft Word (`.docx`) engineering report complete with executive summaries, coordinate conventions, section drawings, 3D/2D schematics, internal force/deflection/stress plots, equilibrium checks, station tables, and verification benchmarks.
- **Customizable Interface:** Choose from **21 visual UI themes** to suit your workspace preferences.

## Workflow

1. **Define Geometry & Material:** Set the beam span, choose a material preset (or enter custom $E$, $G/\nu$, $S_y$, $S_{ut}$, $S_{uc}$, and $\rho$ values), and select preferred units.
2. **Configure Stepped Cross-Sections:** Define one or more axial segments, select standard or custom profiles, and verify $A$, $I_y$, $I_z$, $J$, and stiffness properties in the live dimensioned preview.
3. **Apply 3D Supports & Loads:** Place 6-DOF boundary restraints ($U_x, U_y, U_z, R_x, R_y, R_z$) or bearing presets and apply 3D point forces, distributed loads, bending moments, torques, and optional self-weight.
4. **Analyze 3D Viewport, Diagrams & Stresses:** Inspect the 3D WebGL model and 2D projections, review $V, M, \theta, \delta, N, T,$ and $\phi$ diagrams, explore cross-section stress maps and principal stresses, and check safety factors across all five failure theories.
5. **Verify & Export:** Cross-check results against built-in analytical benchmarks and export figures or a complete `.docx` engineering report.

## Methodology & Accuracy

- **Decoupled 3D Finite Element Solver:** For a straight beam aligned with the global $x$-axis ($y$ vertical, $z$ horizontal), linear-elastic behavior decouples into four independent systems solved via banded Gaussian elimination ($\mathbf{K}\mathbf{u} = \mathbf{F}$):
  - **Bending ($x\text{--}y$ plane):** Deflection $v$ and slope $dv/dx$ (stiffness $EI_z$) modeled with 2-node cubic Hermite Euler–Bernoulli beam elements.
  - **Bending ($x\text{--}z$ plane):** Deflection $w$ and slope $dw/dx$ (stiffness $EI_y$) modeled with 2-node cubic Hermite Euler–Bernoulli beam elements.
  - **Axial Extension:** Displacement $u$ (stiffness $EA$) modeled with 2-node linear bar elements.
  - **Torsion:** Angle of twist $\phi$ (stiffness $GJ$) modeled with 2-node linear bar elements.
- **Adaptive Mesh & Analytical Resultant Reconstruction:** The mesher automatically places nodes at both beam ends, every cross-section step, every support, and all point/distributed load boundaries, subdividing intervals so no element exceeds $L/240$. Trapezoidal distributed loads are integrated into consistent nodal force and moment vectors, support reactions are recovered from $\mathbf{R} = \mathbf{K}\mathbf{u} - \mathbf{F}$, and internal force and torque distributions ($N, V_y, V_z, M_y, M_z, T$) are evaluated analytically from static equilibrium.
- **Benchmark Validation:** Built-in verification cases validate 3D numerical outputs against classical closed-form textbook solutions.

## Future Work

- **Rotating-Bending Fatigue & Endurance Analysis:** Separate reversed bending stresses ($\sigma_a$) from steady torsional and axial mean stresses ($\tau_m, \sigma_m$), incorporating Marin endurance limit factors ($k_a\text{--}k_e$) and Goodman, Gerber, Soderberg, and ASME-Elliptic fatigue safety checks.
- **Shaft Notch & Stress Concentration Factors ($K_t, K_{ts}, K_f, K_{fs}$):** Model shoulder fillet radii, keyways, retaining ring grooves, and press-fit hubs at stepped section transitions.
- **Power-Transmission Component Generators & Bearing Life:** Convert transmitted power ($P$) and shaft speed ($\text{RPM}$) directly into spur, helical, and bevel gear or belt/chain load components, paired with finite bearing stiffnesses, angular misalignment limits, and ISO 281 $L_{10h}$ bearing life calculations.
- **Lateral Critical Speeds (Rotordynamics):** Assemble consistent/lumped mass matrices with mounted disk inertias to compute whirling natural frequencies and critical speeds ($N_{cr}$).
- **Warping Torsion & General 3D Space Frames:** Extend open cross-sections (such as C-sections) with Vlasov warping stiffness ($EC_w$) and generalize the solver to arbitrarily oriented 3D space-frame members.

## License

- No License.
