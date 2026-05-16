---
title: "Spin Valve"
date: 2026-05-16
tags: [micromagnetism, spintronics, gmr, spin-valve]
description: "Two ferromagnetic layers separated by a non-magnetic spacer: a magnetically tunable resistor, and the original device of spintronics."
---

## Intuition

A **spin valve** is the simplest magnetic resistor you can build out of two
ferromagnets. Stack two magnetic layers with a thin non-magnetic conductor
between them and the device's electrical resistance becomes a function of
the *relative orientation* of their magnetizations — **low** when the two
layers are parallel, **high** when they are antiparallel. The reason is
that the conduction electrons themselves carry spin, and each ferromagnetic
layer acts as a **spin filter**: it lets through electrons aligned with its
magnetization much more easily than the opposite spin. Two filters in
series transmit a lot of current when their preferences agree and very
little when they disagree — exactly like crossing two polarizers in
optics. This effect is **giant magnetoresistance (GMR)**, and it underlies
nearly every magnetic sensor and read head built since the 1990s.

## Formal Definition

A **spin valve** is a multilayer of the form

$$
\text{FM}_1 \;|\; \text{NM} \;|\; \text{FM}_2,
$$

with two ferromagnetic layers ($\text{FM}_1$, $\text{FM}_2$) separated by a
thin non-magnetic metallic spacer ($\text{NM}$, e.g. Cu, Cr). The
[[magnetization|magnetizations]] of the two FM layers, $\vec{m}_1$ and
$\vec{m}_2$, make an angle $\theta$. The device's two-terminal resistance
$R(\theta)$ interpolates between the **parallel** and **antiparallel** values:

$$
R(\theta) \;=\; R_P + (R_{AP} - R_P)\,\frac{1-\cos\theta}{2}, \qquad
R_P < R_{AP}.
$$

The **GMR ratio**

$$
\mathrm{GMR} \;\equiv\; \frac{R_{AP} - R_P}{R_P}
$$

quantifies the contrast, typically a few percent to tens of percent in
metallic stacks at room temperature.

## Key Results

### 1. Why the resistance depends on alignment — spin-dependent scattering

In a ferromagnetic metal, the conduction electrons of *majority spin*
(parallel to the local [[magnetization]]) and *minority spin* (antiparallel)
see different densities of states at the Fermi level. They scatter
differently — typically the minority channel resists more. Sorting the
current by spin gives **two resistances in parallel**, one per spin
species: the **Mott two-current model**.

- **Parallel configuration ($\vec{m}_1 \parallel \vec{m}_2$):** the spin-up
  channel is "majority" in both layers and travels easily; the spin-down
  channel is "minority" in both. The low-resistance spin-up channel
  short-circuits the high-resistance one, and the total resistance is low.
- **Antiparallel configuration ($\vec{m}_1 \parallel -\vec{m}_2$):** *every*
  electron is "majority" in one layer and "minority" in the other. Neither
  spin channel finds an easy path, both channels are similarly resistive,
  and the parallel combination is **higher** than in the parallel case.

This is the microscopic content of the Mott two-current model — the
explanation Fert and Grünberg gave for the GMR they each discovered in
1988 (Nobel Prize in Physics, 2007).

### 2. Pedagogical toy model

A useful intuition pump (not literal physics, but the right spirit): treat
each layer as a probabilistic filter that transmits an aligned spin with
high probability and an opposite spin with low probability. Take 50% spin-up,
50% spin-down at the input, and per-layer transmission probabilities
$\sim 90\%$ (aligned) and $\sim 10\%$ (opposite):

| Electron spin | Parallel ($\uparrow\uparrow$) | Antiparallel ($\uparrow\downarrow$) |
| ------------- | ----------------------------- | ----------------------------------- |
| Up | $0.9 \times 0.9 \approx 81\%$ pass | $0.9\times 0.1\approx 9\%$ pass |
| Down | $0.1\times 0.1\approx 1\%$ pass | $0.1\times 0.9\approx 9\%$ pass |
| **Total** | **$\sim 41\%$** | **$\sim 9\%$** |

The parallel stack transmits **much more current** than the antiparallel
stack — i.e. has lower resistance. The same conclusion the two-current
model gives, in cartoon form.

**The crucial subtlety:** scattering is *not* counted layer by layer for
each electron classically. Each spin species is a quantum channel whose
transmission depends on *both* layers — what matters is the
**joint probability** for a spin channel to make it through the stack.

### 3. The atoms don't change — only the spin direction does

Applying a small external field flips the magnetization of the **free**
layer relative to the **pinned** (reference) layer. The
[[magnetic-atom|magnetic atoms]] themselves stay locked in the lattice;
only their *collective spin orientation* rotates. So the device's
resistance is **electrically reconfigurable** by a magnetic field — the
foundation of every modern hard-disk read head.

<!-- TODO: add diagram (spin_valve.png) — FM | NM | FM stack with majority/minority channels -->

## Summary

| Property | Parallel ($\theta=0$) | Antiparallel ($\theta=\pi$) |
| -------- | --------------------- | --------------------------- |
| Resistance | $R_P$ (low) | $R_{AP}$ (high) |
| Spin-up channel | majority everywhere — easy path | majority/minority — blocked once |
| Spin-down channel | minority everywhere — hard | minority/majority — blocked once |
| Net effect | one short-circuit channel | no short-circuit channel |

A spin valve is therefore a **magnetically tunable resistor**. Replace the
metallic spacer with a thin insulating barrier (e.g. MgO) and the same
geometry becomes a [[magnetic-tunnel-junction|magnetic tunnel junction]],
where tunneling magnetoresistance (TMR) replaces GMR with much larger ratios.

## Connections

- [[magnetic-atom]] — bound vs conduction electrons, the prerequisite for spintronics
- [[magnetization]] — what defines the "majority" direction in each layer
- [[spin-polarized-current]] — the current that emerges from a ferromagnetic filter *(stub)*
- [[spin-transfer-torque]] — when the spin-polarized current acts back on $\vec{m}$ *(stub)*
- [[magnetic-tunnel-junction]] — the tunneling cousin of the spin valve *(stub)*

## References

- M. N. Baibich *et al.*, *Phys. Rev. Lett.* **61**, 2472 (1988) — discovery of GMR.
- G. Binasch *et al.*, *Phys. Rev. B* **39**, 4828 (1989) — independent GMR discovery.
- N. F. Mott, *Adv. Phys.* **13**, 325 (1964) — two-current model.
- A. Fert, *Rev. Mod. Phys.* **80**, 1517 (2008) — Nobel lecture, spintronics overview.
