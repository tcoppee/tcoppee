---
title: "Magnetocrystalline Anisotropy"
date: 2026-05-16
tags: [micromagnetism, anisotropy, spin-orbit, easy-axis, uniaxial, cubic]
description: "Why the magnetization of a crystal prefers certain directions: spin-orbit coupling ties the spins to the lattice and creates easy axes — the origin of memory in every magnetic material."
---

## Intuition

A spin in vacuum is rotationally invariant: it can point any direction
with no energy cost. But the same spin in a crystal feels the lattice
*through* its electronic orbitals — and orbitals know all about the
crystal axes. **Spin-orbit coupling** is the bridge: it ties the spin
to the orbital, the orbital to the lattice, and therefore the spin to
the crystal axes.

The energetic consequence is that the magnetization of a ferromagnetic
crystal does **not** point with equal ease in every direction. Some
directions are *easy* — the magnetization settles there spontaneously
— and some are *hard* — pushing $\vec{M}$ there costs measurable
energy.

Without anisotropy there would be no [[hysteresis|hysteresis]], no
[[magnetic-domains|domain walls]], and no magnetic memory at all.
$\vec{M}$ could rotate freely to zero in any soft direction and the
material would forget every bit you wrote on it. Anisotropy is the
reason a refrigerator magnet stays magnetized.

## Formal definition

The **magnetocrystalline anisotropy energy** is the part of the free
energy that depends on the orientation of $\vec{M}$ relative to the
crystal axes. For a single-domain particle of volume $V$ it can always
be expanded in the direction cosines $(\alpha_1, \alpha_2, \alpha_3)$
of $\vec{M}$ along the crystal axes.

Two cases dominate practice:

**Uniaxial (Co hcp, all single-axis crystals):**

$$
E_{\text{ani}} \;\approx\; K_{u1}\,V\,\sin^2\theta \;+\; K_{u2}\,V\,\sin^4\theta \;+\; \dots,
$$

where $\theta$ is the angle between $\vec{M}$ and the easy axis and
$K_{u1}$ is the **uniaxial anisotropy constant** in J/m$^3$.

**Cubic (Fe bcc, Ni fcc):**

$$
E_{\text{ani}} \;\approx\; K_{c1}\,V\,(\alpha_1^2\alpha_2^2 + \alpha_2^2\alpha_3^2 + \alpha_3^2\alpha_1^2) \;+\; \dots
$$

The sign and magnitude of $K_{c1}$ pick out which crystal directions
are easy.

## Key results

### 1. Origin: spin-orbit coupling

The exchange interaction by itself is **isotropic**: it cares only
about relative spin orientation, not absolute direction in space.
What ties the spins to the lattice is the spin-orbit Hamiltonian
$\mathcal{H}_{\text{SO}} \propto \vec{L}\cdot\vec{S}$. Through the
orbital, $\vec{S}$ inherits the symmetry of the local electrostatic
environment, and the anisotropy energy is what survives after
averaging over the partially filled d- or f-shell.

Two consequences follow immediately:

- 4f magnets (rare earths) have **enormous** anisotropy — the f
  orbitals barely hybridize with the lattice so spin-orbit is
  unscreened. SmCo$_5$ and NdFeB inherit anisotropies of
  $10^7$ J/m$^3$.
- 3d magnets (Fe, Co, Ni) have **modest** anisotropy — strong
  hybridization with neighbours quenches most of the orbital
  angular momentum, leaving residual anisotropies of $10^4$ – $10^5$
  J/m$^3$.

### 2. Uniaxial anisotropy and the bit

For $K_{u1} > 0$ the energy is minimal at $\theta = 0$ and $\theta = \pi$
— two equivalent ends of the easy axis. The energy surface looks like
two polar caps; rotating $\vec{M}$ into the equator costs $K_{u1}V$.

These two stable states are the **two minima of one classical bit**.
Every uniaxial ferromagnetic grain — in a hard disk, in an MRAM cell,
in a permanent magnet — is fundamentally a Stoner–Wohlfarth bit
sitting in such a double-well potential. See
[[stoner-wohlfarth|Stoner–Wohlfarth]] for the dynamics.

For $K_{u1} < 0$ the easy *plane* replaces the easy axis: $\vec{M}$
prefers any direction perpendicular to the unique axis, but no
specific direction within that plane — the so-called **easy-plane**
case.

### 3. Cubic anisotropy in Fe and Ni

In a cubic crystal the sign of $K_{c1}$ picks one of two
distinguished sets of directions:

- $K_{c1} > 0$ (Fe): easy axes are the $\langle 100 \rangle$ edges of
  the cube. There are **six** equivalent easy directions, so a single
  cubic crystal can host six possible orientations of $\vec{M}$.
- $K_{c1} < 0$ (Ni): easy axes are the $\langle 111 \rangle$ body
  diagonals, with **eight** equivalent orientations.

Iron and nickel both have several equivalent easy axes, which makes
their magnetic memory richer (and their domain structure more
complicated) than that of a uniaxial cobalt crystal.

### 4. Orders of magnitude

| Material | $K_{u}$ or $|K_{c1}|$ (kJ/m$^3$) | Hardness class | Typical use |
| -------- | ------------------------------- | -------------- | ----------- |
| Permalloy (Ni$_{80}$Fe$_{20}$) | $< 1$ | very soft | sensors, HF transformers |
| Soft Fe | $\sim 50$ | soft | transformer cores |
| Co (hcp) | $\sim 500$ | moderate | thin-film magnets |
| SmCo$_5$ / NdFeB | $10^4$ – $10^5$ | very hard | permanent magnets |

The same number $K_u$ that fixes the [[hysteresis|coercivity]]
$H_K = 2K_u/(\mu_0 M_s)$ also fixes the energy barrier $K_u V$ to
thermal switching — that is why it is *the* central material
parameter of magnetism engineering.

### 5. Beyond magnetocrystalline anisotropy

Anisotropy in a real sample comes from several sources, only one of
which is magnetocrystalline:

- **Shape anisotropy** — stray-field energy of an elongated grain
  prefers $\vec{M}$ along the long axis. Effective anisotropy
  $\frac{1}{2}\mu_0 M_s^2 (N_\perp - N_\parallel)$.
- **Surface / interface anisotropy** — broken symmetry at a film
  surface generates a perpendicular term $K_s / t$. Crucial in MRAM
  free layers.
- **Strain-induced (magnetoelastic)** — strain $\varepsilon$ feeds
  into the energy through the magnetostriction constants $\lambda$.

The [[micromagnetic-energy|micromagnetic energy functional]] lumps all
of these into a single effective anisotropy term.

## Summary

Without anisotropy a ferromagnet has no memory. Magnetocrystalline
anisotropy is the spin-orbit-mediated rule that ties spins to the
crystal lattice: it picks **easy axes**, sets the height of the
double-well bit, and through $H_K = 2K_u/(\mu_0 M_s)$ caps the
coercivity of any single-domain particle.

The contrast between **soft** ($K_u \to 0$) and **hard**
($K_u \gtrsim 10^5$ kJ/m$^3$) materials is the contrast between a
ferromagnet that forgets and one that remembers — and it is set
almost entirely by spin-orbit physics on the atomic scale.

## Connections

- [[micromagnetic-energy]] — anisotropy as one of four competing energies
- [[stoner-wohlfarth]] — the minimal hysteretic model built from $K_u$
- [[hysteresis]] — what anisotropy buys you macroscopically
- [[magnetic-domains]] — domain walls cost $\sqrt{A K_u}$ per area
- [[stoner-model]] — band-magnetism counterpart of the same 3d electrons

## References

- A. Hubert & R. Schäfer, *Magnetic Domains* (Springer, 1998), Ch. 3.
- R. Skomski, *Simple Models of Magnetism* (Oxford, 2008), Ch. 3.
- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Ch. 7.
