---
title: "Larmor Precession"
date: 2026-05-16
tags: [micromagnetism, dynamics, precession, larmor]
description: "The fundamental rotation of a magnetic moment around an effective magnetic field — the conservative core of the LLG equation."
---

## Intuition

Place a [[magnetic-moment|magnetic moment]] $\boldsymbol{\mu}$ in a field
$\vec{B}$ and your first guess is that it snaps into alignment, like a
compass needle. It doesn't. Instead it **precesses** — its tip traces out a
cone around the field direction, at constant angle, like a **spinning top**
under gravity. The reason is that $\boldsymbol{\mu}$ carries angular
momentum: a torque can't simply pull it in, it has to *turn* the angular
momentum vector. The resulting circular motion is **Larmor precession**,
and it is the conservative (energy-preserving) heart of the
[[llg-equation|LLG equation]]: the first term in LLG describes nothing
else. In real magnets, damping eventually closes the cone — but for the
duration of the precession, $|\vec{m}|$ and the angle between $\vec{m}$ and
$\vec{H}^{\text{eff}}$ are both conserved.

## Formal Definition

A magnetic moment in a field experiences a torque

$$
\vec{\tau} \;=\; \boldsymbol{\mu}\times\vec{B}.
$$

Because $\boldsymbol{\mu}$ is proportional to the carrier's angular momentum,
Newton's law for angular momentum ($\dot{\vec{L}} = \vec{\tau}$) becomes an
equation of motion for $\boldsymbol{\mu}$ itself. In micromagnetic notation,
applied to the reduced [[magnetization]] $\vec{m}$ in the
[[effective-field|effective field]] $\vec{H}^{\text{eff}}$, this is the
**Landau–Lifshitz** (precessional) term:

$$
\frac{\partial \vec{m}}{\partial t} \;=\; -\gamma_0\,\vec{m}\times \vec{H}^{\text{eff}},
\qquad \gamma_0 \equiv \mu_0\gamma_G.
$$

The cross product on the right is always perpendicular to $\vec{m}$, so
$|\vec{m}|$ is preserved. Likewise the angle between $\vec{m}$ and
$\vec{H}^{\text{eff}}$ is preserved — only the *azimuthal* angle around
$\vec{H}^{\text{eff}}$ evolves.

## Key Results

### 1. The Larmor frequency

For a static, uniform $\vec{H}^{\text{eff}}$, the equation of motion is
linear and solved by uniform precession at the **Larmor angular frequency**

$$
\omega_L \;=\; \mu_0\,\gamma_G\,H^{\text{eff}} \;=\; \gamma_0\,H^{\text{eff}},
$$

with **Larmor period**

$$
T_L \;=\; \frac{2\pi}{\omega_L}.
$$

The frequency scales **linearly** with the field magnitude — strong fields
mean fast precession.

For an electron, $\gamma_G/2\pi \approx 28\,\mathrm{GHz/T}$, so a field of
$1\,\mathrm{T}$ produces precession at $\sim 28\,\mathrm{GHz}$ — squarely
in the microwave range, which is why ferromagnetic resonance (FMR) lives
there. The numerical value follows directly from the
[[magnetic-moment#3-the-gyromagnetic-ratio|electron gyromagnetic ratio]]
$\gamma_e = g_s\mu_B/\hbar \approx 1.76\times 10^{11}\;\mathrm{rad\,s^{-1}\,T^{-1}}$.

### 1bis. The same physics, three resonances

Larmor precession is the **single mechanism** behind a whole family of
experimental techniques. Only the carrier — and therefore $\gamma$ —
changes:

| Technique | Carrier | Used for |
| --------- | ------- | -------- |
| **EPR / ESR** | unpaired electron spin in a [[magnetic-materials|paramagnet]] | identifying defects, radicals, transition-metal sites |
| **FMR** | the collective magnetization $\vec{M}$ of a ferromagnet | damping $\alpha_G$, anisotropy fields, spin-wave spectra |
| **NMR / MRI** | nuclear spin (mostly $^1$H) — $\gamma_p \approx 2.7\times 10^8$ rad/s/T, $\sim 660\times$ smaller | medical imaging, chemistry, neuroscience |

In all three cases, a static field $\vec{B}_0$ sets the Larmor frequency
$\omega_L = \gamma B_0$, and a transverse microwave (or radiofrequency)
field tuned to $\omega_L$ tips the magnetization. The huge spread of
$\gamma$ across electrons/nuclei is why EPR sits in the **GHz** band
and NMR in the **MHz** band at the same applied field.

### 2. Sense of precession

The minus sign in the equation of motion (inherited from the negative
electron gyromagnetic ratio) makes the precession **clockwise** when viewed
along $\vec{H}^{\text{eff}}$. The motion is purely **kinematic**: no energy
is gained or lost, and the cone angle is fixed by the initial condition.

### 3. With damping — the cone closes

In a real ferromagnet, the Gilbert term of the [[llg-equation|LLG equation]]
adds a viscous torque that pulls $\vec{m}$ toward $\vec{H}^{\text{eff}}$.
The motion becomes a **shrinking spiral** at frequency $\omega_L$, with the
cone angle decaying on the timescale $\tau \sim 1/(\alpha_G\,\omega_L)$
until $\vec{m}\parallel \vec{H}^{\text{eff}}$.

<!-- TODO: add diagram (larmor_precession.png) — cone of precession around H_eff -->

## Summary

| Quantity | Expression | Meaning |
| -------- | ---------- | ------- |
| Torque | $\boldsymbol{\mu}\times\vec{B}$ | drives precession, not alignment |
| Equation of motion | $\partial_t\vec{m} = -\gamma_0\,\vec{m}\times\vec{H}^{\text{eff}}$ | LL (precessional) term of [[llg-equation\|LLG]] |
| Larmor frequency | $\omega_L = \gamma_0\,H^{\text{eff}}$ | rate of precession |
| Period | $T_L = 2\pi/\omega_L$ | one orbit |
| Conserved | $|\vec{m}|$, cone angle | pure precession, no dissipation |

Larmor precession is what gives magnetization its **clock**: every
dynamical phenomenon in micromagnetism — FMR, spin waves, vortex gyration,
STT-driven switching — beats at, or is detuned from, the local Larmor
rhythm.

## Connections

- [[llg-equation]] — Larmor precession is the LL term; add Gilbert damping and STT to get the full equation
- [[effective-field]] — what plays the role of $\vec{H}^{\text{eff}}$ in a real micromagnet
- [[magnetic-moment]] — the carrier whose angular momentum makes precession happen
- [[magnetization]] — the field that precesses in the continuum theory
- [[thiele-equation]] — gyrotropic vortex motion is a collective-coordinate cousin of Larmor precession

## References

- J. Larmor, *Phil. Mag.* **44**, 503 (1897) — original derivation.
- C. Kittel, *Introduction to Solid State Physics*, ch. on magnetic resonance.
- D. D. Stancil & A. Prabhakar, *Spin Waves: Theory and Applications* (Springer, 2009).
