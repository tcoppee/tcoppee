---
title: "Thiele Equation"
date: 2026-05-16
tags: [micromagnetism, dynamics, vortex, thiele, stvo]
description: "Collective-coordinate reduction of the LLGS equation: vortex-core motion as a quasiparticle under gyrotropic, restoring, damping, and spin-transfer forces."
---

## Intuition

The full [[llg-equation|LLGS equation]] is a continuum equation of motion
for $\vec{m}(\vec{r}, t)$ — millions of degrees of freedom in a typical
simulation. But many magnetic textures (vortices, skyrmions, domain walls)
are **rigid objects**: they translate and rotate without changing their
internal shape. For such textures it is enough to track a single
**collective coordinate** — the position $\vec{X}(t)$ of the texture's
center — and the entire LLGS dynamics collapses to a Newton-like equation
on $\vec{X}$. For a **magnetic vortex core** in a thin ferromagnetic disk
this reduction is the **Thiele equation**, and the vortex core moves like a
**charged particle in a magnetic field** living in the plane.

## Formal Definition

For a rigid magnetization texture $\vec{m}(\vec{r}, t) = \vec{m}_0(\vec{r} - \vec{X}(t))$,
inserting the ansatz into the LLGS equation and integrating over space
yields the **Thiele equation**:

$$
\boxed{\;
\bar{\bar M}\cdot\ddot{\vec{X}} \;+\; \bar{\bar G}\cdot \dot{\vec{X}}
\;=\; -\,\nabla_{\vec{X}} W
\;-\; \bar{\bar D}\cdot \dot{\vec{X}}
\;+\; \vec{F}_{\text{ext}}
\;}
$$

where, evaluated for the rigid profile $\vec{m}_0$,

- $\bar{\bar M}$ — **mass tensor** (usually negligible for thin films),
- $\bar{\bar G}$ — **gyrotropic tensor**, producing a Magnus-like
  transverse force,
- $-\nabla_{\vec{X}} W$ — **restoring force** from the confinement energy
  $W(\vec{X})$,
- $\bar{\bar D}$ — **damping tensor**, the collective image of Gilbert
  dissipation,
- $\vec{F}_{\text{ext}}$ — **external forces**, notably the
  [[spin-transfer-torque|spin-transfer torque]] in current-driven devices.

## Key Results

### 1. Thin-disk reduction (the form used in practice)

For a thin circular free layer of thickness $L$ hosting a **magnetic vortex**,
the planar symmetry collapses the tensors to scalars / a single vector:

$$
\vec{G}\times \dot{\vec{X}} \;=\; -\,k\,\vec{X}
\;-\; D\,\dot{\vec{X}}
\;+\; \vec{F}_{\text{ext}},
\qquad \vec{G} = G\,\hat{e}_z,
$$

so that the gyrotropic term becomes

$$
\bar{\bar G}\cdot \dot{\vec{X}} \;=\; G\,(\hat{e}_z\times \dot{\vec{X}}).
$$

The constants have transparent micromagnetic meanings:

- **Gyrovector magnitude:**
$$
G \;=\; -\,\frac{2\pi\, p\, L\, M_s}{\gamma_0},
$$
  where $p = \pm 1$ is the **vortex-core polarity** (out-of-plane direction
  of $\vec{m}$ at the core). The sign of $G$ determines the **sense of
  gyration**.
- **Confinement stiffness:** $k$ comes from the quadratic expansion of the
  magnetostatic + exchange energy in $\vec{X}$ near the center: $W(\vec{X})
  \approx \tfrac{1}{2}k|\vec{X}|^2$.
- **Damping coefficient:** $D \propto \alpha_G$ — the collective image of
  Gilbert damping in the rigid-profile reduction.

### 2. Free gyrotropic motion

With $\vec{F}_{\text{ext}} = 0$ and $D = 0$, the Thiele equation reduces to

$$
G\,(\hat{e}_z\times\dot{\vec{X}}) \;=\; -k\,\vec{X},
$$

whose solution is **circular gyration** of the core around the disk center
at the **gyrotropic frequency**

$$
\omega_G \;=\; \frac{k}{|G|}.
$$

This is the eigenmode that dominates the low-frequency response of vortex
disks — the working point of [[spin-torque-vortex-oscillator|STVOs]].

### 3. Force balance under spin-transfer torque

Adding a current-induced force $\vec{F}_{\text{STT}}$ from the
[[spin-transfer-torque|Slonczewski torque]] gives the **steady-state**
balance

$$
\vec{G}\times \dot{\vec{X}} \;-\; k\,\vec{X} \;=\; \vec{F}_{\text{STT}} \;-\; D\,\dot{\vec{X}}.
$$

Above a critical current, $\vec{F}_{\text{STT}}$ overcomes damping and the
core enters **sustained auto-oscillation** on a stable limit cycle — the
operating regime of a vortex-based nano-oscillator.

## Summary

| Term | Meaning | Role |
| ---- | ------- | ---- |
| $\bar{\bar M}\cdot \ddot{\vec{X}}$ | Inertial | Usually negligible in thin films |
| $\bar{\bar G}\cdot \dot{\vec{X}}$ | Gyrotropic | Magnus-like transverse force; sign set by core polarity $p$ |
| $-\nabla_{\vec{X}} W$ | Restoring | Confinement of the texture |
| $\bar{\bar D}\cdot \dot{\vec{X}}$ | Damping | Gilbert dissipation, collective form |
| $\vec{F}_{\text{ext}}$ | Driving | Spin-transfer torque, applied fields |

The Thiele equation turns a continuum LLGS problem into a **2D Newton
equation for the vortex core**, exposing the gyrotropic eigenmode and the
spin-transfer-driven limit cycles that power STVOs.

## Connections

- [[llg-equation]] — the full continuum equation from which Thiele is derived
- [[spin-transfer-torque]] — origin of $\vec{F}_{\text{ext}}$ in spintronic devices
- [[magnetic-vortex]] — the topological texture whose center is $\vec{X}$ *(stub)*
- [[gyrovector]] — geometric origin of $\vec{G}$ *(stub)*
- [[spin-torque-vortex-oscillator]] — device exploiting the gyrotropic mode *(stub)*

## References

- A. A. Thiele, *Phys. Rev. Lett.* **30**, 230 (1973) — the original derivation.
- D. L. Huber, *Phys. Rev. B* **26**, 3758 (1982).
- K. Yu. Guslienko, *J. Nanosci. Nanotechnol.* **8**, 2745 (2008) — vortex Thiele dynamics.
- B. A. Ivanov & C. E. Zaspel, *Phys. Rev. Lett.* **99**, 247208 (2007).
