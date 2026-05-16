---
title: "Scales in Magnetism"
date: 2026-05-16
tags: [micromagnetism, modeling, dft, atomistic, multiscale]
description: "From DFT to atomistic spin to micromagnetics: three computational scales, their domains of validity, and why ℓex sets the boundary between them."
---

## Intuition

A piece of iron has $\sim 10^{23}$ electrons. No simulation will ever
follow them all. So magnetism is a **multiscale** subject: each scale
keeps only the degrees of freedom that matter at that resolution, and
hands the *parameters* it produces up to the next scale.

Three scales dominate:

- **Ab-initio (DFT)** — every electron explicit, on the scale of
  angstroms and femtoseconds.
- **Atomistic spin** — one classical vector per atom, on the scale of
  nanometers and picoseconds.
- **Micromagnetics** — a continuous field $\vec{M}(\vec{r}, t)$, on the
  scale of $10$–$10^4$ nm and nanoseconds to microseconds.

Each scale is the *coarse-graining* of the previous one. The boundary
between them is set by the **[[micromagnetic-energy#exchange|exchange
length]]** $\ell_{\text{ex}} = \sqrt{2A/(\mu_0 M_s^2)} \sim 5$–$10$ nm:
below it, the spin field doesn't really vary, so a continuum is fine;
above it, even atomistic models become wasteful.

## Formal hierarchy

| Scale | Method | Length | Time | DoF | What it computes |
| ----- | ------ | ------ | ---- | --- | ---------------- |
| Quantum | **DFT** | $\sim 0.1$ nm | fs | electrons $\psi_i(\vec{r})$ | atomic moments, $A$, $K_u$, exchange integrals $J$ |
| Atomic | **atomistic spin** | $\sim 1$ nm | ps | one $\vec{S}_i$ per atom | thermodynamics at $T \to T_C$, ultrafast switching |
| Continuum | **micromagnetics** | $5$–$10^4$ nm | ns–µs | $\vec{m}(\vec{r}, t)$ | domain walls, vortices, devices, hysteresis |

Each upper level **inherits parameters** from the level below:
DFT gives the exchange stiffness $A$, anisotropy $K_u$, and atomic
moment $\mu$ that the atomistic spin model uses; the atomistic model
in turn provides the saturation magnetization $M_s(T)$ and damping
$\alpha_G$ used by [[llg-equation|LLG]] micromagnetic simulations.

## Key results

### 1. Why a continuum is allowed at all

The continuum approximation rests on a single observation: in a
ferromagnet, **exchange enforces parallel alignment over a length
$\ell_{\text{ex}}$**. On scales much shorter than that, the spin field
is essentially uniform — there is nothing for a finer description to
resolve. On scales much longer, atomic granularity disappears
entirely. The "useful" window where $\vec{m}(\vec{r})$ varies smoothly
but appreciably is exactly the regime where micromagnetics works.

This is the same physics that makes the Navier–Stokes equation a
useful description of water even though water is made of molecules:
the molecular mean free path is the analogue of $\ell_{\text{ex}}$.

### 2. Where each scale wins

- **DFT** is essential when the *atomic moment itself* matters —
  determining whether an interface is ferro- or antiferromagnetic,
  computing $K_u$ of an interface, predicting tunneling spin
  polarizations.
- **Atomistic spin** is the right tool for **finite-temperature**
  thermodynamics ($T_C$, critical exponents) and for ultrafast
  laser-driven demagnetization (sub-picosecond dynamics where the
  continuum picture is suspect).
- **Micromagnetics** is the workhorse for **devices**: hard-disk read
  heads, MRAM cells, spin-torque oscillators, domain-wall race-track
  memories. Tools: OOMMF, MuMax3, MagPar, Fidimag.

### 3. Multiscale handoff

The standard recipe to design a new spintronic stack is:

1. **DFT** the stack — get $M_s$, $A$, $K_u$, interfacial $P$, $\Delta E_F^\uparrow - \Delta E_F^\downarrow$.
2. Feed those parameters into a **micromagnetic** simulation of the
   device geometry, with the LLG-Slonczewski equation if currents
   matter.
3. Compare to measured switching curves, FMR spectra, R(H) loops.
4. Iterate by adjusting the stack composition.

The big computational bottleneck is step 2: the **magnetostatic
field** $\vec{H}^{\text{ms}}$ is nonlocal and dominates simulation
cost. State-of-the-art codes accelerate it with FFT, FMM, or tensor
methods on GPUs.

## Summary

Magnetism is a three-scale subject:

- **DFT** (electrons, fs, 0.1 nm) — *what* an atom's moment is and
  how it talks to its neighbors.
- **Atomistic spin** (one $\vec{S}$ per atom, ps, nm) — finite-$T$
  thermodynamics, ultrafast switching.
- **Micromagnetics** ($\vec{m}(\vec{r}, t)$, ns, $10$–$10^4$ nm) —
  domain walls, vortices, devices.

The boundary that sets the continuum approximation is the **exchange
length** $\ell_{\text{ex}} \sim 5$–$10$ nm. The rest of this wiki
lives at the third scale.

## Connections

- [[micromagnetic-energy]] — the continuum energy functional itself
- [[llg-equation]] — the dynamics equation solved at the micromagnetic scale
- [[magnetic-domains]] — sub-µm structures naturally captured by micromagnetics
- [[stoner-model]] — itinerant-electron picture that lives at the DFT scale

## References

- A. Aharoni, *Introduction to the Theory of Ferromagnetism* (Oxford, 2000), Ch. 9.
- R. F. L. Evans et al., *Atomistic Spin Model Simulations of Magnetic Nanomaterials*, J. Phys. Condens. Matter **26**, 103202 (2014).
- A. Vansteenkiste et al., *The design and verification of MuMax3*, AIP Adv. **4**, 107133 (2014).
