---
title: "LLG Equation"
date: 2026-05-16
tags: [micromagnetism, dynamics, llg, spintronics]
description: "The equation of motion for the magnetization: precession, Gilbert damping, and the Slonczewski spin-transfer torque (LL → LLG → LLGS)."
---

## Intuition

A ferromagnet's magnetization $\vec{m}$ behaves like a **gyroscope**: when you
push it with a magnetic field, it doesn't simply align with the field — it
**precesses** around it, just as a spinning top precesses around gravity.
Real magnets also lose energy (to the lattice, to electrons, to spin waves),
so the precession slowly **spirals inward** until $\vec{m}$ comes to rest
along the effective field. And in modern spintronic devices, an electrical
current carrying angular momentum can give the magnet an extra "kick" —
a [[spin-transfer-torque|spin-transfer torque]] — which can sustain
oscillations or even switch the magnetization. The **Landau–Lifshitz–Gilbert
(LLG)** equation, in its full Slonczewski form, packages all three effects
into a single equation of motion for the unit vector $\vec{m} = \vec{M}/M_s$.

## Formal Definition

The full equation of motion, including spin-transfer torque, is the
**Landau–Lifshitz–Gilbert–Slonczewski (LLGS)** equation:

$$
\boxed{\;
\frac{\partial \vec{m}}{\partial t} \;=\; -\gamma_0\,\vec{m} \times \vec{H}^{\text{eff}}
\;+\; \alpha_G\,\vec{m} \times \frac{\partial \vec{m}}{\partial t}
\;+\; \vec{\tau}^{\,\text{ST}}
\;}
$$

with

- $\vec{m}(\vec{r}, t) = \vec{M}/M_s$ the unit [[magnetization]] vector ($|\vec{m}|=1$),
- $\vec{H}^{\text{eff}}$ the [[effective-field|effective field]] (sum of
  exchange, anisotropy, demagnetizing, and Zeeman contributions),
- $\gamma_0 = \mu_0 \gamma_G$ where $\gamma_G$ is the **gyromagnetic ratio** —
  the constant relating angular momentum and magnetic moment,
- $\alpha_G \ll 1$ the dimensionless **Gilbert damping** coefficient,
- $\vec{\tau}^{\,\text{ST}}$ the Slonczewski [[spin-transfer-torque|spin-transfer torque]].

The constraint $|\vec{m}|=1$ is built in: each torque term lies in the plane
perpendicular to $\vec{m}$, so only the *direction* of $\vec{m}$ changes,
never its magnitude.

## Key Results

### 1. Pure precession — the Landau–Lifshitz (LL) equation

In the absence of damping and external torques:

$$
\frac{\partial \vec{m}}{\partial t} = -\gamma_0\,\vec{m} \times \vec{H}^{\text{eff}}.
$$

This drives the [[larmor-precession|Larmor precession]] of $\vec{m}$ around
$\vec{H}^{\text{eff}}$. The minus sign reflects the negative gyromagnetic
ratio of the electron: precession is **clockwise** when viewed along
$\vec{H}^{\text{eff}}$. Energy is conserved — the cone angle never closes.

### 2. Adding dissipation — the Gilbert torque

Real magnets dissipate energy through spin–lattice and spin–electron
couplings. Gilbert added a **viscous torque**

$$
\vec{\tau}^{\,G} = \alpha_G\,\vec{m} \times \frac{\partial \vec{m}}{\partial t},
$$

which is perpendicular to $\partial_t \vec{m}$ and points inward in the
precessional plane. Inserting it gives the **LLG equation**:

$$
\frac{\partial \vec{m}}{\partial t} = -\gamma_0\,\vec{m} \times \vec{H}^{\text{eff}}
\;+\; \alpha_G\,\vec{m} \times \frac{\partial \vec{m}}{\partial t}.
$$

The cone angle now closes monotonically: $\vec{m}$ spirals toward
$\vec{H}^{\text{eff}}$. Typical values of $\alpha_G$ range from $\sim 10^{-4}$
(YIG) to $\sim 10^{-2}$ (Co, Fe alloys).

### 3. Explicit form

The LLG equation is *implicit* in $\partial_t \vec{m}$. Taking the cross
product with $\vec{m}$ on the left and using $|\vec{m}|=1$ yields the
mathematically equivalent **explicit Landau–Lifshitz form**:

$$
(1+\alpha_G^2)\,\frac{\partial \vec{m}}{\partial t}
= -\gamma_0\,\vec{m}\times \vec{H}^{\text{eff}}
\;-\; \gamma_0\,\alpha_G\,\vec{m}\times(\vec{m}\times \vec{H}^{\text{eff}}).
$$

This is the form used by most micromagnetic solvers (e.g. MuMax3, OOMMF).

### 4. Spin-transfer torque — the LLGS equation

In [[magnetic-tunnel-junction|MTJs]] and spin-valve nanopillars, a
[[spin-polarized-current|spin-polarized current]] transfers angular momentum
to the local magnetization. The **Slonczewski torque** has the canonical form

$$
\vec{\tau}^{\,\text{ST}} \;=\; \gamma_0\,a_J\,\vec{m}\times(\vec{m}\times\vec{p})
\;+\; \gamma_0\,b_J\,\vec{m}\times\vec{p},
$$

where $\vec{p}$ is the unit polarization vector (set by a reference layer),
and $a_J$, $b_J$ encode the **damping-like** and **field-like** components,
both proportional to the current density $J$. The damping-like term competes
directly with $\alpha_G$: above a critical current $J_c$ it can sustain
auto-oscillations (as in [[spin-torque-vortex-oscillator|STVOs]]) or switch
the free-layer magnetization (the basis of STT-MRAM).

## Summary

| Term | Name | Role |
| ---- | ---- | ---- |
| $-\gamma_0\,\vec{m}\times\vec{H}^{\text{eff}}$ | Precessional (LL) | [[larmor-precession\|Larmor precession]] around $\vec{H}^{\text{eff}}$ |
| $\alpha_G\,\vec{m}\times\partial_t \vec{m}$ | Gilbert damping | Drives alignment with $\vec{H}^{\text{eff}}$ |
| $\vec{\tau}^{\,\text{ST}}$ | Spin-transfer torque | Current-induced torque (MTJs, spin valves) |

## Connections

- [[effective-field]] — what enters $\vec{H}^{\text{eff}}$ and how it's computed
- [[larmor-precession]] — the precessional motion driven by the LL term
- [[spin-transfer-torque]] — origin and structure of $\vec{\tau}^{\,\text{ST}}$
- [[spin-polarized-current]] — how the polarization $\vec{p}$ arises
- [[magnetic-tunnel-junction]] — the device in which LLGS is most often applied
- [[thiele-equation]] — collective-coordinate reduction for rigid textures (vortex core)

## References

- L. Landau & E. Lifshitz, *Phys. Z. Sowjet.* **8**, 153 (1935).
- T. L. Gilbert, *IEEE Trans. Magn.* **40**, 3443 (2004) — phenomenological damping.
- J. C. Slonczewski, *J. Magn. Magn. Mater.* **159**, L1 (1996) — spin-transfer torque.
- W. F. Brown Jr., *Micromagnetics* (Interscience, 1963).
