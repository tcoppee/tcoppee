---
title: "Magnetic Moment"
date: 2026-05-16
tags: [micromagnetism, foundations, magnetic-moment, spin]
description: "The atomic-scale vector that quantifies how something behaves like a tiny magnet — origin of all magnetism."
---

## Intuition

A **magnetic moment** is the vector that says "this object behaves like a
tiny bar magnet, of *this* strength, pointing *this* way." It is the
microscopic seed of all magnetism. At the atomic scale it comes from two
sources — the orbital motion of electrons around the nucleus, and their
intrinsic [[spin]]. Add the contributions of all the electrons in an atom
and you get the **atomic magnetic moment**; sum atomic moments over a piece
of material and you get the body's [[magnetization|magnetization]]. The
entire ladder of magnetism — from a single electron to a permanent magnet —
is built by adding magnetic moments.

## Formal Definition

The magnetic moment $\boldsymbol{\mu}$ is the vector that relates the
**torque** an object feels in an external magnetic field $\vec{B}$ to the
field itself:

$$
\vec{\tau} \;=\; \boldsymbol{\mu}\times\vec{B}.
$$

For a continuous magnetized body of volume $V$, the **total magnetic
moment** is the volume integral of the [[magnetization]]:

$$
\vec{m}_{\text{tot}} \;=\; \int_V \vec{M}(\vec{r})\, dV \qquad [\mathrm{A\cdot m^2}].
$$

A magnetic moment $\boldsymbol{\mu}$ also generates a dipolar magnetic field
in its surroundings — the field of a "point magnet."

## Key Results

### 1. Two sources at the atomic scale

In an atom, electrons contribute a magnetic moment through:

1. **Orbital motion** — an electron circulating around the nucleus is a
   tiny current loop, generating an orbital moment
   $\boldsymbol{\mu}_L = -\,\frac{\mu_B}{\hbar}\vec{L}$.
2. **Intrinsic [[spin]]** — every electron carries an irreducible spin
   angular momentum $\vec{S}$, with associated moment
   $\boldsymbol{\mu}_S = -\,g_s\,\frac{\mu_B}{\hbar}\vec{S}$,
   where $g_s \approx 2$ is the **electron spin g-factor**.

Spin therefore contributes **twice as much** magnetic moment per unit of
angular momentum as the orbital motion — an irreducibly quantum
relativistic effect, predicted by the Dirac equation. The natural unit of
either contribution is the **Bohr magneton**

$$
\mu_B \;=\; \frac{e\hbar}{2 m_e} \;\approx\; 9.274\times 10^{-24}\,\mathrm{A\cdot m^2}.
$$

The total atomic moment is the sum over all electrons; in many cases only
the **unpaired** electrons contribute (paired spins cancel). The combined
orbital + spin contribution of a one-electron atom is written compactly
as

$$
\boldsymbol{\mu} \;=\; \boldsymbol{\mu}_L + \boldsymbol{\mu}_S \;=\; -\,\mu_B\,(\vec{L} + 2\vec{S})/\hbar,
$$

with the conspicuous factor **2** in front of the spin — Landé's $g_s$
factor, a strictly relativistic effect that drops out of the Dirac
equation. Spin contributes *twice* as much moment as the equivalent
orbital angular momentum, and that factor is what makes spin-dominated
elements (Fe, Co, Ni) magnetically loud.

### 3. The gyromagnetic ratio

Because both the magnetic moment and the angular momentum scale linearly
with the same electron, they are **rigidly proportional**:

$$
\boldsymbol{\mu} \;=\; -\,\gamma_e\,\vec{L},
\qquad
\gamma_e \;=\; \frac{g_s\,\mu_B}{\hbar} \;\approx\; 1.76\times 10^{11}\;\mathrm{rad\,s^{-1}\,T^{-1}}.
$$

The proportionality constant $\gamma_e$ is the **gyromagnetic ratio** of
the electron. Its physical importance is enormous: in an external field
$\vec{B}$ the moment does *not* line up instantaneously but **precesses**
at the Larmor frequency $\omega_L = \gamma_e B$ — exactly like a spinning
top under gravity. This single equation is the foundation of:

- **EPR** (electron paramagnetic resonance),
- **FMR** (ferromagnetic resonance),
- **NMR / MRI** (with $\gamma_p \ll \gamma_e$ for the proton),
- the dynamical [[llg-equation|LLG equation]] of micromagnetism.

See [[larmor-precession]] for the geometry.

### 4. From atomic moments to macroscopic magnetization

In a **ferromagnet**, the [[exchange-interaction|exchange interaction]]
locks neighboring atomic moments parallel inside [[magnetic-domains|domains]].
The **domain magnetic moment** is the vector sum

$$
\vec{m}_{\text{domain}} \;=\; \sum_{i\in\text{domain}} \boldsymbol{\mu}_i,
$$

and the macroscopic [[magnetization]] is the density of such moments:
$\vec{M} = d\vec{m}_{\text{tot}}/dV$. This is the conceptual ladder from
quantum mechanics to a fridge magnet.

<!-- TODO: add diagram (magnetic_moment.png) — illustration of a magnetic dipole and its field -->

## Notation Warning

Several conventions are in active use. **In this wiki:**

| Symbol | Meaning | Units |
| ------ | ------- | ----- |
| $\boldsymbol{\mu}$ | Microscopic / atomic magnetic moment ("quantum" notation) | A·m² |
| $\vec{m}_{\text{tot}}$ | Total magnetic moment of a body, $\int_V \vec{M}\,dV$ | A·m² |
| $\vec{M}$ | [[magnetization]] (moment per unit volume) | A/m |
| $\vec{m} = \vec{M}/M_s$ | **Reduced magnetization** (everywhere else in this wiki) | dimensionless |

Many textbooks write $\vec{m}$ for the magnetic moment instead of
$\boldsymbol{\mu}$ — the two are equivalent there, but **inside this wiki**
the symbol $\vec{m}$ is reserved for the reduced magnetization $\vec{M}/M_s$.

## Summary

A magnetic moment is the vector that quantifies the strength and direction
of the magnetic field produced by — and the torque felt by — a microscopic
source. At the atomic scale it originates from electron spin and orbital
motion. At the macroscopic scale, the collective alignment of many atomic
moments produces the [[magnetization]] of the material.

## Connections

- [[magnetic-atom]] — which atoms carry a non-zero moment, and why
- [[magnetization]] — the continuum field built from atomic moments
- [[spin]] — intrinsic source of half the atomic moment *(stub)*
- [[exchange-interaction]] — what aligns neighboring atomic moments *(stub)*
- [[magnetic-domains]] — regions of parallel moments

## References

- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Ch. 3.
- D. J. Griffiths, *Introduction to Electrodynamics*, §6.1 — magnetic dipoles.
- B. D. Cullity & C. D. Graham, *Introduction to Magnetic Materials* (Wiley, 2009).
