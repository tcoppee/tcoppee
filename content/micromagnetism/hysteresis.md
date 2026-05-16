---
title: "Hysteresis"
date: 2026-05-16
tags: [micromagnetism, hysteresis, coercivity, remanence, soft-magnet, hard-magnet]
description: "The M(H) loop, its three key numbers (Ms, Mr, Hc), the area-equals-loss rule, and the soft-vs-hard dichotomy that governs every magnetic application."
---

## Intuition

Apply a slowly varying field $H(t)$ to a ferromagnet and watch its
magnetization. Unlike a paramagnet, the response is **history-dependent**:
$M$ at a given $H$ depends on whether you arrived from $+H_{\max}$ or
from $-H_{\max}$. Plot $M$ versus $H$ over one full cycle and you get
a closed loop — the **hysteresis curve**.

That single picture is the **identity card** of a ferromagnetic
material. Its shape decides whether the material is good for a
transformer core, a permanent magnet, a read head, or a memory cell.
Three numbers on the loop carry almost all the engineering
information, and the area of the loop is literally the energy lost
per cycle.

## Formal definition

Take an initially demagnetized sample, sweep $H$ from $0$ to $+H_{\max}$,
back to $-H_{\max}$, and back to $+H_{\max}$. The resulting trajectory
$M(H)$ has:

- a **virgin curve** that leaves the origin on first magnetization,
- two **saturation plateaux** at $\pm M_s$ for $|H| \gtrsim H_K$,
- a **descending branch** from $+M_s$ at $+H_{\max}$ to $-M_s$ at
  $-H_{\max}$,
- a symmetric **ascending branch** on the way back.

The three quantities that label the loop are:

| Symbol | Name | Definition |
| ------ | ---- | ---------- |
| $M_s$ | **Saturation magnetization** | $M$ at $H \to \infty$ — an intrinsic property of the material |
| $M_r$ | **Remanence** | $M$ at $H = 0$ on the descending branch — what the magnet "remembers" |
| $H_c$ | **Coercivity** | $H$ at which $M = 0$ on the descending branch — the field needed to erase the magnet |

The **squareness** $M_r / M_s$ tells how well the magnet retains its
remanence; the area enclosed by the loop is the energy dissipated per
unit volume per cycle.

## Key results

### 1. Loop area = energy loss per cycle

For one closed loop, the work done by the source per unit volume is

$$
W \;=\; \mu_0 \oint H\,dM \;=\; \mu_0 \,(\text{area of the loop}).
$$

This energy is irreversibly converted into **heat** — through domain-wall
friction, eddy currents, and microscopic Barkhausen jumps. In a
transformer running at 50 Hz, that loss happens 50 times per second
and is the dominant source of core heating.

### 2. The soft–hard dichotomy

Two extreme designs dominate applications:

| | Soft magnets | Hard magnets |
| --- | --- | --- |
| Coercivity $H_c$ | $< 1$ kA/m | $> 10$ kA/m, up to $10^6$ |
| Loop shape | thin, low-area | wide, high-area |
| Remanence | low to moderate | high |
| Anisotropy $K_u$ | small | large |
| Typical materials | soft Fe, permalloy (Ni$_{80}$Fe$_{20}$), Mn–Zn ferrite | NdFeB, SmCo$_5$, AlNiCo, Sr/Ba ferrite |
| Used for | transformers, read heads, sensors | permanent magnets, motors, loudspeakers, MRAM bits |

The compromise is fundamental: a **soft magnet** minimizes
$H_c$ and loop area (low loss, high permeability); a **hard magnet**
maximizes $M_r$ and $H_c$ (strong, stable remanence). No single
material wins both.

### 3. What sets the coercivity

In an ideal [[stoner-wohlfarth|Stoner–Wohlfarth]] single-domain particle,

$$
H_c \;=\; \frac{2 K_u}{\mu_0 M_s} \;=\; H_K
$$

is the **anisotropy field** — purely intrinsic. In real materials,
[[magnetic-domains|domain-wall nucleation and pinning]] determine
$H_c$, and measured values are typically 10–100× smaller than $H_K$.
This gap, **Brown's paradox**, makes coercivity an *extrinsic*
property sensitive to microstructure, defects, grain size and surface
treatment. The same alloy can have $H_c$ varying by a factor of 100
depending on processing.

### 4. Minor loops and the virgin curve

A loop swept between $\pm H_{\max} < \pm H_K$ is a **minor loop**, with
smaller area, smaller remanence, and a smaller effective coercivity.
The **virgin curve** (first magnetization from a demagnetized state)
is *inside* the major loop because the as-cooled domain structure has
$M = 0$ on average.

These distinctions matter in practice: a permanent magnet's "remanence"
is whatever it was last saturated to, which need not be $M_s$ if the
magnet was never fully saturated during manufacturing.

## Limits

- Loops shown here assume **quasi-static** sweeping ($\omega \to 0$).
  At finite frequency, eddy currents and viscous wall motion broaden
  the loop further. The full frequency dependence is captured by the
  [[llg-equation|LLG equation]] coupled to Maxwell's equations.
- Real samples have **demagnetizing fields** that shear the loop
  along the $H$ axis. The "intrinsic" loop $M$ vs the *internal* field
  $H_{\text{int}} = H_{\text{ext}} - N M$ is what we plot here; the
  *experimental* loop $M$ vs $H_{\text{ext}}$ is always sheared.

## Summary

Hysteresis is a ferromagnet's identity card. Three numbers carry the
engineering content:

- $M_s$ — how much magnetization is available,
- $M_r$ — how much survives at zero field,
- $H_c$ — how big a reverse field is needed to wipe it out.

Their product, together with the loop area, dictates whether the
material belongs in a transformer core (small $H_c$, small area) or
in a permanent magnet (large $M_r$, large $H_c$). Everything else in
this wiki — domains, anisotropy, dynamics — eventually feeds back
into the shape of this curve.

## Connections

- [[stoner-wohlfarth]] — the minimal model of a hysteretic single-domain particle
- [[magnetocrystalline-anisotropy]] — sets the maximum possible $H_c$
- [[magnetic-domains]] — domain walls and pinning are what makes real $H_c$ smaller than $H_K$
- [[magnetic-materials]] — where ferromagnets sit among the five families
- [[llg-equation]] — what happens to $\vec{m}(\vec{r}, t)$ during a single irreversible jump

## References

- B. D. Cullity & C. D. Graham, *Introduction to Magnetic Materials* (Wiley, 2009), Chs. 11–13.
- A. Hubert & R. Schäfer, *Magnetic Domains* (Springer, 1998).
- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Ch. 11.
