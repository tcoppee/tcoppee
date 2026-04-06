---
title: Research
description: Research on spin-torque vortex oscillators and spintronic neuromorphic architectures at UCLouvain IMCN.
tags: [research]
---

My PhD research sits at the intersection of **nanomagnetism**, **spintronics**, and **unconventional computing**. The central object of study is the **spin-torque vortex oscillator (STVO)** — a nanoscale magnetic device whose rich nonlinear dynamics make it a promising candidate as a physical neuron in brain-inspired hardware.

I work within the [Neuromorphic Engineering Group (NEnG)](https://perso.uclouvain.be/flavio.abreuaraujo/) at UCLouvain's IMCN institute, under the supervision of **Prof. Flavio Abreu Araujo** and **Dr. Tristan da Câmara Santa Clara Gomes**.

---

## Spin-Torque Vortex Oscillators

A spin-torque vortex oscillator is a nanopillar device in which a spin-polarized current drives the steady precession of a magnetic vortex core. This produces a microwave-frequency electrical signal whose frequency, amplitude, and phase are highly sensitive to the applied current and external conditions — making STVOs inherently nonlinear and tuneable oscillators.

Their key properties for neuromorphic applications include:
- **Nonlinearity** — the oscillator responds non-trivially to inputs, enabling complex transformations
- **Memory** — the vortex core retains information about recent inputs through its phase dynamics
- **Tunability** — frequency and amplitude can be controlled via dc current or applied field

---

## Neuromorphic Computing with STVOs

The broader goal of my PhD is to harness these properties for **spintronic neuromorphic hardware**. In reservoir computing, a network of nonlinear dynamical nodes (the "reservoir") transforms input signals into a high-dimensional representation, which is then read out by a simple linear layer. STVOs serve as ideal physical reservoir nodes.

My work builds on the framework developed in the group, notably the **hybrid Thiele Equation Approach (hybrid TEA)**, which combines the accuracy of full micromagnetic simulations with the computational speed of analytical models. This allows efficient simulation of STVO dynamics for neuromorphic tasks — a tool I use and aim to extend during my PhD.

$$\frac{d\vec{X}}{dt} = \frac{1}{G}\left(\vec{F}_\text{STT} + \vec{F}_\text{conf} + \vec{F}_\text{Oersted}\right)$$

---

## PhD Work Packages

My thesis is structured around five work packages over four years:

| WP | Title | Period |
|----|-------|--------|
| WP1 | Analytical modelling and experimental preparation | Year 1–2 |
| WP2 | Experimental measurements and micromagnetic simulations | Year 1–2 |
| WP3 | Hybrid Thiele calibration and experimental validation | Year 2–3 |
| WP4 | Coupling and neuromorphic functionality | Year 3–4 |
| WP5 | Dissemination, open-source tools, and thesis writing | Year 1–4 |

**WP1** establishes the analytical framework linking STVO device parameters to measurable observables, including a sensitivity analysis and implementation of a numerical solver.

**WP2** covers the experimental characterisation of individual STVOs and the use of MuMax3 micromagnetic simulations to benchmark models against measurements.

**WP3** uses the hybrid TEA to bridge the gap between model and experiment, building parametric corrections from multi-device validation data.

**WP4** investigates dipolar coupling between STVOs and explores STVO networks as prototypes for neuromorphic circuits.

---

## Methods & Tools

**Simulation:** MuMax3 (micromagnetic), Python, COMSOL, custom STVO solvers  
**Circuits & modelling:** LTSpice, Eldo, Cadence, Verilog-AMS  
**Experimental (in training):** RF/dc electrical characterisation, magnetotransport measurements

---

## Group & Collaborations

| Partner | Institution | Topic |
|---------|-------------|-------|
| Prof. Flavio Abreu Araujo | UCLouvain (NEnG) | PhD supervisor — STVO neuromorphic hardware |
| Dr. Tristan da Câmara Santa Clara Gomes | INESC-MN, Portugal / UCLouvain | PhD co-supervisor — spintronic neuromorphic computing |

The NEnG group collaborates broadly with SPINTEC (CEA/CNRS, Grenoble), INL (Braga), C2N (CNRS, Palaiseau), Bar-Ilan University, and UT Dallas.

---

## Key References

1. J. Grollier *et al.*, "Neuromorphic spintronics," *Nature Electronics* **3**, 360–370 (2020).
2. D. Marković *et al.*, "Physics for neuromorphic computing," *Nature Rev. Physics* **2**, 499–510 (2020).
3. J. Torrejon *et al.*, "Neuromorphic computing with nanoscale spintronic oscillators," *Nature* **547**, 428–431 (2017).
4. V. S. Pribiag *et al.*, "Magnetic vortex oscillator driven by dc spin-polarized current," *Nature Phys.* **3**, 498–503 (2007).
5. A. Moureaux *et al.*, "Neuromorphic spintronics accelerated by an unconventional data-driven Thiele equation approach," *arXiv*:2301.11025 (2023).
6. F. A. Araujo, C. Chopin & S. De Wergifosse, "Ampere–Oersted field splitting of the nonlinear STVO dynamics," *Sci. Rep.* **12**, 10605 (2022).
