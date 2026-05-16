---
title: "Micromagnetism"
tags: [micromagnetism, index]
description: "Entry point to a living wiki on micromagnetism — the continuum theory of magnetization at the mesoscopic scale."
---

## Welcome

This is a **digital garden** on **micromagnetism** — the continuum theory that
describes how the magnetization $\vec{M}(\vec{r}, t)$ of a ferromagnet evolves
in space and time. It sits between the atomistic world of individual spins and
the macroscopic world of bulk magnetic materials, and it is the language used
to model everything from **magnetic domain walls** and **skyrmions** to the
switching dynamics inside the **MRAM cell** in your computer.

Pages here are written for **two readers at once**: a researcher who wants
rigorous math, and a newcomer who wants to *feel* the physics first. Each note
opens with intuition, then formal definitions, then key results — so you can
read as shallow or as deep as you need.

## Why micromagnetism?

A piece of ferromagnetic iron contains $\sim 10^{23}$ spins. Treating each one
quantum-mechanically is hopeless. But on scales larger than a few nanometers,
the magnetization varies smoothly, and we can replace the discrete lattice of
spins with a **continuous unit vector field**

$$
\vec{m}(\vec{r}, t) = \frac{\vec{M}(\vec{r}, t)}{M_s}, \qquad |\vec{m}| = 1.
$$

Micromagnetism is the variational theory built on this field — balancing
exchange, anisotropy, magnetostatic, and Zeeman energies — and its time
evolution is governed by the [[llg-equation|Landau–Lifshitz–Gilbert equation]].

## Table of contents

### Foundations
- [[magnetic-atom]] — What makes an atom magnetic in the first place
- [[magnetic-moment]] — The atomic-scale seed of magnetism
- [[magnetization]] — The vector field $\vec{M}(\vec{r})$ at the heart of it all
- [[magnetic-materials]] — Diamagnetic, paramagnetic, ferromagnetic
- [[modeling-scales]] — DFT, atomistic spin, and the micromagnetic continuum
- [[micromagnetic-energy]] — Exchange, magnetostatic, Zeeman, anisotropy
- [[magnetocrystalline-anisotropy]] — Spin-orbit coupling and easy axes
- [[magnetic-domains]] — Why ferromagnets break into domains

### Ferromagnetism
- [[stoner-model]] — Itinerant ferromagnetism and the Stoner criterion
- [[stoner-wohlfarth]] — The minimal single-domain hysteretic nano-magnet
- [[hysteresis]] — The $M(H)$ loop, $M_s$, $M_r$, $H_c$, soft vs hard

### Magnetization dynamics
- [[llg-equation]] — Prprocecession, damping, and spin-transfer torque
- [[larmor-precession]] — How $\vec{m}$ orbits the effective field
- [[effective-field]] — The driver of dynamics: $\vec{H}^{\text{eff}}$

### Vortex dynamics
- [[thiele-equation]] — Collective-coordinate equation for the vortex core

### Spintronics
- [[spin-valve]] — Magnetoresistive FM/NM/FM stack; origin of GMR
- [[spin-polarized-current]] — Currents that carry net spin angular momentum
- [[spin-transfer-torque]] — How a spin current torques a magnet (LLGS, STT-MRAM, STNO)
- [[magnetic-tunnel-junction]] — The MTJ, Jullière TMR, and MRAM

### Beyond ferromagnetism
- [[superconductivity]] — Meissner, BCS, Type I vs II, Abrikosov vortices, applications

## How to navigate

Every page cross-links to its neighbors via `[[wikilinks]]`. There is no
single "right" reading order — follow the links as a trail. If you are new,
start here, then read [[llg-equation]], and branch out from there. The
**graph view** in the right sidebar shows the wiki's structure at a glance.
