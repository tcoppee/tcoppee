---
title: "Spin-Transfer Torque (STT)"
date: 2026-05-16
tags: [spintronics, stt, llgs, slonczewski, mram, oscillator]
description: "When a spin-polarized current flows through a ferromagnet, it dumps angular momentum into the local magnetization. The result: current-driven switching (STT-MRAM) and current-driven oscillations (STNO)."
---

## Intuition

Push a spin-polarized current through a ferromagnetic film. Each
electron carries an angular momentum $\hbar/2$ in its spin. Inside
the film the electron must align its spin to the local exchange field
— and by conservation of angular momentum, what the electron loses,
the magnetization gains. A *current* therefore exerts a *torque* on
the magnetization, with no external magnetic field needed.

Predicted by Slonczewski (1996) and Berger (1996), demonstrated
experimentally by Tsoi (1998) and Katine (2000), this **spin-transfer
torque** (STT) has become the workhorse of modern spintronics. The
same effect drives two seemingly opposite phenomena:

- If the torque is **dissipative-like**, the current writes a new
  magnetization state. This is the writing mechanism of STT-MRAM.
- If the torque is **anti-dissipative**, the current sustains a
  steady-state precession. This is the spin-torque nano-oscillator
  (STNO).

## Formal definition

Add a Slonczewski term to the [[llg-equation|LLG equation]] for the
free-layer reduced magnetization $\vec{m}(\vec{r}, t)$:

$$
\boxed{\;\frac{\partial \vec{m}}{\partial t} \;=\; -\mu_0\gamma_e\,\vec{m}\times \vec{H}^{\text{eff}} \;+\; \alpha_G\,\vec{m}\times\frac{\partial \vec{m}}{\partial t} \;+\; \gamma_e\,a_J\,\vec{m}\times(\vec{m}\times\vec{m}_p)\;}
$$

where $\vec{m}_p$ is the **polarization direction** (the magnetization
of the reference layer) and $a_J$ is the Slonczewski torque amplitude,

$$
a_J \;=\; \frac{\hbar\,P\,J}{2 e\,\mu_0\,M_s\,t},
$$

with $J$ the current density, $P$ the spin polarization, $t$ the
free-layer thickness, and $e$ the electron charge. This is the
**LLGS equation**.

The Slonczewski term has the same geometric form as Gilbert damping —
both are double cross products $\vec{m}\times(\vec{m}\times\hat{\boldsymbol{\xi}})$ —
but with **opposite signs** depending on current direction. Hence STT
acts like either *extra* damping or *negative* damping.

## Key results

### 1. Current-driven switching

When STT acts as **extra damping** towards $\vec{m}_p$, the free layer
relaxes to its anti-parallel or parallel state with very low energy
cost. The Sun–Slonczewski critical current density to switch a uniaxial
single-domain free layer is

$$
J_c \;=\; \frac{2 e\,\alpha_G\,\mu_0\,M_s\,t}{\hbar\,P}\,\Big( H_K + H_{\text{ext}} + \tfrac{1}{2} M_s \Big).
$$

Typical numbers: $J_c \sim 10^6$–$10^8$ A/cm$^2$ — enormous in absolute
units, but easy to reach through a nanometer-thin pillar of $\sim 30$ nm
diameter. This is the writing mechanism of **STT-MRAM** and the reason
modern MRAM cells dispense with inductive write lines.

### 2. Current-driven oscillation (STNO)

When the current flows the *other* way, the Slonczewski term acts as
**negative damping**: it amplifies precession instead of damping it.
Steady-state is reached when negative STT damping exactly compensates
Gilbert damping. The free layer then **precesses indefinitely** at a
frequency set by $\vec{H}^{\text{eff}}$ and tunable by $J$ — typically
$1$–$50$ GHz.

These **spin-torque nano-oscillators** are highly compact (few tens
of nm), tunable, and CMOS-compatible — they are studied for microwave
sources, RF mixing, and **neuromorphic computing** (a single STNO can
emulate a neuron).

### 3. Macrospin picture and stability boundary

For a macrospin in the linearized regime, the LLGS equation reduces
to an ordinary differential equation in the cone angle $\theta(t)$
with an effective damping

$$
\alpha_{\text{eff}}(J) \;=\; \alpha_G - \frac{\hbar P J}{2 e\,\mu_0\,M_s\,t\,H_{\text{eff}}}.
$$

- $\alpha_{\text{eff}} > 0$ → relaxation, switching path.
- $\alpha_{\text{eff}} < 0$ → growing precession, oscillator path.
- $\alpha_{\text{eff}} = 0$ → the critical current $J_c$ above.

This single sign change governs every STT device.

### 4. Spin-Hall variant

A separate but related mechanism — **spin-orbit torque (SOT)** —
generates a spin current via the spin-Hall effect in a heavy metal
(Pt, Ta, W) underneath the free layer. SOT decouples read and write
paths, allowing better endurance and lower error rates, and is now
displacing STT in the highest-performance MRAM cells.

## Summary

A spin-polarized current carries angular momentum; flowing through a
ferromagnet, it transfers that momentum to the local magnetization.
Adding the Slonczewski term to LLG gives the **LLGS equation** of
modern spintronics:

- one current direction → **writing**, the basis of **STT-MRAM**;
- the opposite direction → **sustained precession**, the basis of
  **spin-torque nano-oscillators**.

The critical current ($J \sim 10^6$–$10^8$ A/cm$^2$) is large in
absolute units but easily reached in nanometer-thin pillars. STT, and
its cousin SOT, are the physical mechanism behind almost every active
spintronic device in production today.

## Connections

- [[llg-equation]] — the equation STT extends
- [[magnetic-tunnel-junction]] — where STT writing actually happens
- [[spin-polarized-current]] — the carrier of the torque
- [[spin-valve]] — historical context: GMR pillars were the first STT testbeds
- [[thiele-equation]] — vortex-core STT dynamics

## References

- J. C. Slonczewski, *J. Magn. Magn. Mater.* **159**, L1 (1996).
- L. Berger, *Phys. Rev. B* **54**, 9353 (1996).
- D. Ralph & M. Stiles, *J. Magn. Magn. Mater.* **320**, 1190 (2008) — review.
- A. D. Kent & D. C. Worledge, *Nat. Nanotechnol.* **10**, 187 (2015).
