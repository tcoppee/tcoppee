---
title: "Stoner–Wohlfarth Model"
date: 2026-05-16
tags: [micromagnetism, hysteresis, single-domain, coercivity, anisotropy]
description: "The simplest model of a hysteretic ferromagnet: a single-domain uniaxial particle in an external field. Predicts the switching field, the astroid, and sets the scale for magnetic recording."
---

## Intuition

How small must a ferromagnetic particle be before it stops splitting
into [[magnetic-domains|domains]] and behaves as one rigid macrospin?
And once it does, how does its magnetization respond to a field?

The **Stoner–Wohlfarth model** (1948) is the minimal answer: take a
single uniaxial nano-particle, assume it stays uniformly magnetized
during reversal (no domain wall, no buckling, no curling), and add one
[[magnetocrystalline-anisotropy|easy axis]] plus one external field.
Two energy terms, one angle. From this toy problem comes the whole
language of **switching fields**, **coercivity** versus angle, and the
*astroid* that engineers still use to design [[#magnetic-recording|magnetic-recording media]].

## Formal definition

Consider an ellipsoidal single-domain particle of volume $V$, saturation
magnetization $M_s$, and uniaxial anisotropy constant $K_u > 0$. Let
$\phi$ be the angle between the **easy axis** and the applied field
$\vec{H}$, and $\theta$ the angle between $\vec{M}$ and $\vec{H}$.
The Stoner–Wohlfarth energy is then a single function of $\theta$:

$$
E(\theta,\phi) \;=\; V\,\Big[\,K_u\,\sin^2(\theta - \phi) \;-\; \mu_0\,M_s\,H\,\cos\theta\,\Big].
$$

The first term is the [[magnetocrystalline-anisotropy|uniaxial
anisotropy energy]] (minimal when $\vec{M}$ lies along the easy axis);
the second is the **Zeeman energy** (minimal when $\vec{M}$ is parallel
to $\vec{H}$).

## Key results

### 1. Two stable states, one bit of memory

At $H = 0$, the energy has two minima at $\theta = \phi$ and
$\theta = \phi + \pi$ — the two ends of the easy axis. The barrier
between them is

$$
\Delta E \;=\; K_u V,
$$

setting the lifetime of each magnetization state through the Arrhenius
law $\tau \propto \exp(K_u V / k_B T)$. This is why magnetic-recording
media must have **large $K_u V$** to keep written bits stable for
years.

### 2. Switching field and coercivity

For the field aligned with the easy axis ($\phi = 0$), one barrier
collapses when

$$
\boxed{\;H_{\text{sw}}(\phi=0) \;=\; H_K \;=\; \frac{2 K_u}{\mu_0 M_s}\;}.
$$

This is the **anisotropy field** — the upper bound on the coercivity
of a single-domain particle, and the natural scale of every hysteresis
loop in this wiki.

For general $\phi$, the switching field is given by the
**Stoner–Wohlfarth astroid**:

$$
H_{\text{sw}}(\phi) \;=\; \frac{H_K}{\left(\sin^{2/3}\!\phi + \cos^{2/3}\!\phi\right)^{3/2}},
$$

an astroid-shaped curve when plotted in the $(H_\parallel, H_\perp)$
plane. The lowest switching field, $H_{\text{sw}} = H_K/2$, occurs at
$\phi = 45^\circ$ — counter-intuitive but crucial for engineering
realistic write fields in MRAM and hard-disk technology.

### 3. The single-particle hysteresis loop

Sweep $H$ from $+\infty$ to $-\infty$ at fixed $\phi$:

- For $\phi = 0$ the magnetization stays rigidly along the easy axis
  and flips abruptly at $H = -H_K$. The loop is a **perfect rectangle**
  of width $2 H_K$ and remanence $M_s$.
- For $0 < \phi < 90^\circ$ the loop becomes sheared: $\vec{M}$ rotates
  reversibly toward $\vec{H}$, then jumps when one minimum disappears.
- For $\phi = 90^\circ$ no jump occurs — the loop closes into a straight
  line. Reversal is fully reversible and the coercivity vanishes.

The set of single-particle loops over $\phi$ generates the textbook
"family of S-shapes" plotted on every Stoner–Wohlfarth figure.

### 4. From single particle to real magnets

Real ferromagnets are made of many grains with different anisotropy
axes. Averaging the Stoner–Wohlfarth loop over a random orientation
distribution gives the **Stoner–Wohlfarth coercivity**:

$$
H_c^{\,\text{SW}} \;\approx\; 0.48\, H_K \;=\; 0.96 \,\frac{K_u}{\mu_0 M_s}.
$$

Measured coercivities in bulk magnets are almost always **lower** than
this — by factors of 10–100 — because [[magnetic-domains|domain walls]],
nucleation defects and thermal activation provide easier reversal
pathways. The gap between $H_c^{\,\text{SW}}$ and measured $H_c$ is
known as **Brown's paradox** and motivates much of modern magnetism
research.

## Application: magnetic recording {#magnetic-recording}

Every bit on a hard disk is, to first approximation, a Stoner–Wohlfarth
particle:

- $M_s$ sets the **read signal** — bigger is better.
- $K_u V$ sets the **thermal stability** — bigger is better.
- $H_K = 2K_u/(\mu_0 M_s)$ sets the **write field** — smaller is better.

These three demands pull in opposite directions, and the resulting
*trilemma* is the central design problem of magnetic-recording media.
Heat-assisted recording (HAMR) sidesteps it by temporarily reducing
$K_u$ during writing.

## Summary

Two energy terms, one angle: the Stoner–Wohlfarth model is the minimal
nano-magnet. It predicts:

- two stable states with a barrier $K_u V$,
- a switching field $H_K = 2K_u/(\mu_0 M_s)$ on the easy axis,
- an astroid switching surface in the $(H_\parallel, H_\perp)$ plane,
- a polycrystalline coercivity $\approx 0.48\,H_K$.

Modern micromagnetism builds on the same picture but lets
$\vec{m}(\vec{r}, t)$ vary in space and time — recovering domain walls,
vortices and the [[llg-equation|LLG dynamics]] that the Stoner–Wohlfarth
ansatz forbids.

## Connections

- [[magnetocrystalline-anisotropy]] — where $K_u$ comes from
- [[hysteresis]] — what $H_c$, $M_r$, and $M_s$ mean macroscopically
- [[micromagnetic-energy]] — the energy terms that survive when $\vec{m}$ is allowed to vary
- [[magnetic-domains]] — how the single-domain assumption breaks down
- [[llg-equation]] — dynamics that interpolate between SW stable states

## References

- E. C. Stoner & E. P. Wohlfarth, *Phil. Trans. Roy. Soc. A* **240**, 599 (1948).
- A. Hubert & R. Schäfer, *Magnetic Domains* (Springer, 1998), Ch. 3.
- R. Skomski, *Simple Models of Magnetism* (Oxford, 2008), Ch. 4.
