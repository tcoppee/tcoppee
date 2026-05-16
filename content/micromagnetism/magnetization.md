---
title: "Magnetization"
date: 2026-05-16
tags: [micromagnetism, foundations, magnetization]
description: "The magnetization vector field M(r): magnetic moment per unit volume, bridging the atomic and macroscopic scales."
---

## Intuition

Inside a magnetic material, every atom carries a tiny **magnetic moment** —
a microscopic compass needle, born from unpaired electron spins and orbital
motion. Most of the time these compass needles point every which way and
their effects cancel. But when they line up — spontaneously, as in a
ferromagnet, or under an applied field — the material as a whole acquires a
**net magnetic character**. The **magnetization** $\vec{M}$ is the
field that captures this collective alignment: at every point in space, it
tells you the density and direction of the local magnetic moments. It is the
quantity that ultimately *is* the magnet.

## Formal Definition

The **magnetization** $\vec{M}(\vec{r})$ is the **magnetic moment per unit
volume**:

$$
\vec{M}(\vec{r}) \;=\; \lim_{\Delta V \to 0}\;\frac{\Delta \boldsymbol{\mu}}{\Delta V}
\qquad [\mathrm{A/m}],
$$

where $\Delta \boldsymbol{\mu} = \sum_{i\in\Delta V}\boldsymbol{\mu}_i$ is the
sum of the [[magnetic-moment|atomic magnetic moments]] contained in a small
volume $\Delta V$ around $\vec{r}$. The limit is taken
in the **continuum sense**: $\Delta V$ is small on the macroscopic scale but
large compared to the atomic lattice, so that $\vec{M}$ varies smoothly.

In a saturated ferromagnet, $|\vec{M}| = M_s$, the **saturation
magnetization** — a material-specific constant. Micromagnetics works with
the **reduced (unit) magnetization**

$$
\vec{m}(\vec{r}, t) \;=\; \frac{\vec{M}(\vec{r}, t)}{M_s}, \qquad |\vec{m}| = 1,
$$

which is the field whose dynamics are governed by the [[llg-equation|LLG equation]].

## Key Results

### 1. What $\vec{M}$ encodes

The magnetization vector field captures three pieces of information at once:

1. The **density of magnetic dipoles** in the material.
2. The **degree of alignment** of those dipoles.
3. The **direction** of the net alignment.

### 2. Bridging scales

While a single [[magnetic-moment|magnetic moment]] $\boldsymbol{\mu}$
is a property of an *individual* atom or ion (units: A·m²), the
magnetization $\vec{M}$ is a *macroscopic field* (units: A/m). Magnetization
is the **continuum coarse-graining** that lets us forget the lattice and
treat the magnet as a continuous medium — the starting point of
micromagnetism.

### 3. Role in Maxwell's equations — B, H, and M

Magnetization enters macroscopic electromagnetism through the constitutive
relation

$$
\vec{B} \;=\; \mu_0\bigl(\vec{H} + \vec{M}\bigr).
$$

The three fields play **distinct roles**:

- $\vec{B}$ — the magnetic flux density: what is *really* present inside
  the matter, and what determines the Lorentz force on a moving charge.
- $\vec{H}$ — the magnetic field: tied to **free currents** (the currents
  the experimentalist controls), i.e. what is "imposed from outside."
- $\vec{M}$ — the **response of the material**: the density of magnetic
  moments induced by, or pre-existing in, the medium.

So $\vec{M}$ is exactly the source of the difference between $\vec{H}$ and
$\vec{B}$ in matter. Spatial variations of $\vec{M}$ act as **bound
currents** and **magnetic charges** that source the stray (demagnetizing)
field $\vec{H}^{\text{ms}}$ — the nonlocal ingredient of the
[[micromagnetic-energy|magnetostatic energy]].

### 4. Linear response: susceptibility and permeability

For most non-ferromagnetic materials, and for ferromagnets in weak fields
away from saturation, the response is **linear**:

$$
\vec{M} \;=\; \chi\,\vec{H},
\qquad
\vec{B} \;=\; \mu_0(1+\chi)\,\vec{H} \;\equiv\; \mu_0\,\mu_r\,\vec{H},
$$

with

- $\chi$ — the (dimensionless) **magnetic susceptibility**, which can be
  positive, negative, or strongly direction-dependent,
- $\mu_r = 1 + \chi$ — the **relative permeability** of the medium.

The sign and magnitude of $\chi$ are what classify materials as
diamagnetic, paramagnetic, or ferromagnetic — see
[[magnetic-materials]] for the full taxonomy.

### 5. Remanent magnetization

In a **ferromagnetic material**, $\vec{M}$ can remain non-zero *after* the
external field is removed:

$$
\vec{M}_r \;=\; \vec{M}(\vec{H}^{\text{ext}} = 0)\qquad \text{(remanence)}.
$$

This is the defining feature of permanent magnets — and a direct consequence
of [[hysteresis|hysteresis]] in the domain structure.

## Summary

| Quantity | Symbol | Units | Scale |
| -------- | ------ | ----- | ----- |
| Magnetic moment | $\boldsymbol{\mu}$ | A·m² | atomic (single dipole) |
| Magnetization | $\vec{M}$ | A/m | continuum (density of moments) |
| Saturation magnetization | $M_s$ | A/m | material constant |
| Reduced magnetization | $\vec{m} = \vec{M}/M_s$ | dimensionless | $|\vec{m}|=1$ |

Magnetization tells us **how magnetized a material is**, **in what
direction**, and **at every point in space** — the foundational field of
micromagnetism.

## Connections

- [[magnetic-moment]] — the atomic-scale building block
- [[llg-equation]] — dynamics of the reduced field $\vec{m}$
- [[micromagnetic-energy]] — energy functional $W[\vec{m}]$
- [[magnetic-domains]] — spatial structure of $\vec{M}$ at equilibrium
- [[hysteresis]] — origin of remanent magnetization *(stub)*

## References

- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Ch. 2.
- B. D. Cullity & C. D. Graham, *Introduction to Magnetic Materials* (Wiley, 2009).
