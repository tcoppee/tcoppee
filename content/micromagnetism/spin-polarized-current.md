---
title: "Spin-Polarized Current"
date: 2026-05-16
tags: [spintronics, spin-polarization, dos, half-metal]
description: "Why a current flowing out of a ferromagnet carries a net spin: asymmetric density of states at the Fermi level and the polarization P = (J↑−J↓)/(J↑+J↓)."
---

## Intuition

In an ordinary metal (Cu, Al), every conduction electron is just as
likely to be spin-up as spin-down, and the current is **unpolarized**:
$J_\uparrow = J_\downarrow$. Pass that same current through a
ferromagnet, however, and the situation changes radically.

Inside a ferromagnet, the [[stoner-model|Stoner exchange splitting]]
rigidly shifts the two spin sub-bands relative to each other. As a
consequence, the **densities of states at the Fermi level** for the
two spin channels are different:

$$
g_\uparrow(\varepsilon_F) \;\neq\; g_\downarrow(\varepsilon_F).
$$

The current that *emerges* from the ferromagnet is then biased
towards the majority spin. The ferromagnet acts as a **spin filter** —
it both magnetizes ($M \neq 0$) and *polarizes its current*. This dual
role is the cornerstone of [[#applications|spintronics]].

## Formal definition

Define the **spin polarization** of a current $\vec{J}$ as

$$
P \;=\; \frac{J_\uparrow - J_\downarrow}{J_\uparrow + J_\downarrow}, \qquad |P| \le 1.
$$

$P = 0$ is an unpolarized current; $P = \pm 1$ is a fully polarized
current carried by a single spin channel. In a two-current model
(Mott, 1936) the two spin channels conduct **in parallel** with
different conductivities $\sigma_\uparrow$, $\sigma_\downarrow$, so

$$
P \;\approx\; \frac{\sigma_\uparrow - \sigma_\downarrow}{\sigma_\uparrow + \sigma_\downarrow} \;\sim\; \frac{g_\uparrow(\varepsilon_F) - g_\downarrow(\varepsilon_F)}{g_\uparrow(\varepsilon_F) + g_\downarrow(\varepsilon_F)},
$$

with corrections coming from the spin-dependent Fermi velocity and
scattering rate.

## Key results

### 1. Typical polarizations

For the elemental 3d ferromagnets and a few engineered materials:

| Material | $P$ (%) | Notes |
| -------- | ------- | ----- |
| Fe | 40–45 | |
| Co | 35–45 | |
| Ni | 25–35 | |
| Permalloy (Ni$_{80}$Fe$_{20}$) | 35–45 | the workhorse soft FM in spintronics |
| CrO$_2$ | $\to 100$ | **half-metal**, only one spin channel at $\varepsilon_F$ |
| Heusler alloys (Co$_2$MnSi, …) | $\to 100$ | designer half-metals |

A **half-metal** is the holy grail of spintronics: $P = 1$ would give
infinite [[#GMR|GMR]] and [[magnetic-tunnel-junction|TMR]] ratios.
Practical half-metals work only at low temperature and lose
polarization at room temperature through spin-flip scattering.

### 2. Spin accumulation and the spin diffusion length

When a spin-polarized current crosses an interface into a non-magnetic
metal, the imbalance does *not* disappear instantly. The two spin
channels relax back to equilibrium over the **spin-diffusion length**
$\lambda_{\text{sf}}$:

$$
\lambda_{\text{sf}} \;=\; \sqrt{D\,\tau_{\text{sf}}},
$$

where $D$ is the diffusion constant and $\tau_{\text{sf}}$ the
spin-flip relaxation time. Typical values: Cu $\sim 500$ nm at 4 K,
Al $\sim 1$ µm, Pt $\sim 5$ nm (large spin-orbit, fast spin-flip).
**Devices must be smaller than $\lambda_{\text{sf}}$** for spin to
survive transit; this is the reason GMR/TMR stacks have layer
thicknesses of only a few nanometers.

### 3. Measuring P

$P$ is not directly observable but inferred from:

- **Point-contact Andreev reflection (PCAR)** — a superconducting tip
  on the FM forces every electron to find a spin-flipped partner; the
  fraction that fails to do so reveals $P$.
- **Tunneling spectroscopy (Meservey–Tedrow)** — splitting of a
  superconducting tip's DOS in a magnetic field.
- **Indirectly**, from the [[#GMR|GMR]] or [[magnetic-tunnel-junction|TMR]] ratio via
  the Jullière model.

## Applications {#applications}

A spin-polarized current is the carrier of every spintronic device:

- It is **read** in [[spin-valve|GMR]] and [[magnetic-tunnel-junction|TMR]]
  stacks — different relative orientations of the two FM layers give
  different resistances.
- It is **written** by [[spin-transfer-torque|spin-transfer torque]] —
  a polarized current dumps its angular momentum into a free layer
  and flips its magnetization.
- It is the active ingredient of every commercial MRAM cell, every
  modern hard-disk read head, and every proposed neuromorphic
  spintronic oscillator.

The fact that a single phenomenon — asymmetric DOS at $\varepsilon_F$
— underlies all of these is the unifying message of the lecture.

## Summary

Inside a ferromagnet the two spin sub-bands have different DOS at
$\varepsilon_F$. The current that leaves the ferromagnet inherits
this imbalance and carries a **spin polarization**
$P = (J_\uparrow - J_\downarrow)/(J_\uparrow + J_\downarrow)$.
Typical 3d ferromagnets give $P \sim 30$–$45\%$; engineered half-metals
approach $P = 100\%$. Spin survives in a non-magnetic conductor only
over the spin-diffusion length $\lambda_{\text{sf}}$, which is why
useful spintronic devices are nanometer-thin.

## Connections

- [[stoner-model]] — origin of the asymmetric DOS
- [[spin-valve]] — how P is read out via GMR
- [[magnetic-tunnel-junction]] — how P is read out via TMR
- [[spin-transfer-torque]] — how P is used to *write* a magnetic state
- [[magnetic-materials]] — where ferromagnets sit among the five families

## References

- N. F. Mott, *Proc. Roy. Soc. A* **153**, 699 (1936) — two-current model.
- I. Žutić, J. Fabian & S. Das Sarma, *Spintronics: Fundamentals and Applications*, Rev. Mod. Phys. **76**, 323 (2004).
- R. Meservey & P. M. Tedrow, *Phys. Rep.* **238**, 173 (1994).
