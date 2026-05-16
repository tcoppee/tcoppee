---
title: "Magnetic Tunnel Junction"
date: 2026-05-16
tags: [spintronics, tmr, mtj, mram, jullière]
description: "The MTJ stack (FM/insulator/FM), tunnel magnetoresistance via the Jullière formula, and the MTJ as the storage cell of every commercial MRAM."
---

## Intuition

Replace the non-magnetic *metal* spacer of a [[spin-valve|GMR spin valve]]
with a *thin insulator* (typically MgO, $\sim 1$ nm). The conduction
electrons can no longer cross classically; they must **tunnel**. The
tunneling probability depends sensitively on whether the wavefunctions
of the two electrodes overlap — and because each electrode is
ferromagnetic with an [[spin-polarized-current|asymmetric DOS]] at the
Fermi level, the tunneling current ends up depending on the *relative
orientation* of the two magnetizations.

The result is **tunnel magnetoresistance (TMR)**: a low resistance when
both ferromagnets are aligned (lots of matching states) and a high
resistance when they are antiparallel (the majority of one electrode
finds only minority states in the other). Effects of 600 % at room
temperature are routinely measured in MgO-based stacks — an order of
magnitude beyond what GMR can deliver, and large enough that a single
MTJ can serve as a non-volatile **memory bit**.

## Formal definition

A **magnetic tunnel junction** (MTJ) is a three-layer stack:

$$
\text{FM}_1 \;/\; \text{insulator} \;/\; \text{FM}_2,
$$

with the insulator thin enough ($\sim 1$–$2$ nm) for quantum tunneling
to dominate. The **TMR ratio** is

$$
\mathrm{TMR} \;\equiv\; \frac{R_{\text{AP}} - R_{\text{P}}}{R_{\text{P}}},
$$

where $R_{\text{P}}$ and $R_{\text{AP}}$ are the resistances when the
magnetizations are parallel and antiparallel.

In the **Jullière model** (1975), tunneling is spin-conserving and
spin-channel resistances add in parallel. This gives

$$
\boxed{\;\mathrm{TMR} \;=\; \frac{2\,P_1\,P_2}{1 - P_1 P_2}\;}
$$

in terms of the [[spin-polarized-current|spin polarizations]] $P_1$
and $P_2$ of the two electrodes. Two consequences are immediate:

- A half-metal ($P = 1$) electrode gives **infinite** Jullière TMR.
- TMR is **always positive** in the Jullière model — the parallel
  configuration is always more conducting.

## Key results

### 1. Three generations of barrier

| Barrier | Year | TMR @ 300 K | Mechanism |
| ------- | ---- | ----------- | --------- |
| Ge, amorphous | 1975 (Jullière) | 14 % @ 4 K | proof-of-principle |
| AlO$_x$ | 1995 (Moodera, Miyazaki) | 30–70 % | first room-temperature MTJ |
| MgO (001), crystalline | 2004 (Yuasa, Parkin) | up to 600 % | **symmetry filtering** of $\Delta_1$ Bloch states |

Crystalline MgO does much more than the Jullière model predicts:
its band structure **filters** the tunneling wavefunctions by symmetry.
Only the $\Delta_1$ Bloch states of bcc Fe and CoFeB couple to the
$\Delta_1$ evanescent state in MgO, and those states are *completely
spin-polarized* — so the effective $P$ approaches unity for the
relevant channel, sending TMR sky-high.

### 2. The MTJ as a memory cell

An MTJ has exactly two stable states (P and AP), separated by a
controllable energy barrier set by the [[magnetocrystalline-anisotropy|anisotropy]]
of the free layer:

- One layer is **pinned** (its magnetization is fixed by an adjacent
  antiferromagnet through exchange biasing).
- The other layer is **free** and stores one bit by pointing parallel
  ("0") or antiparallel ("1") to the pinned reference.

Reading the bit is just a resistance measurement. Writing the bit is
the difficult part — see [[spin-transfer-torque|STT]] for the modern
solution.

### 3. MRAM — non-volatile DRAM-class memory

A **Magnetoresistive Random-Access Memory** (MRAM) array is a 2D grid
of MTJs, one per cell. Each cell stores a non-volatile bit in the
free-layer magnetization and is read out by sensing $R_{\text{P}}$ vs
$R_{\text{AP}}$.

| | SRAM | DRAM | Flash | MRAM (STT-MRAM) |
| --- | ---- | ---- | ----- | -------------- |
| Speed (R/W) | very fast | fast | slow (W) | fast |
| Density | low | high | high | medium |
| Endurance | $\to \infty$ | $\to \infty$ | $\sim 10^5$ writes | $\gtrsim 10^{15}$ writes |
| Volatility | volatile | volatile | non-volatile | **non-volatile** |
| Power | high (leakage) | refresh power | high (writes) | very low |

MRAM combines DRAM-class density and SRAM-class speed with Flash-class
non-volatility — the long-standing memory holy grail. Commercial
STT-MRAM has been shipping since around 2018 (Everspin, Intel, Samsung,
TSMC) and is now found in last-level caches and IoT microcontrollers.

### 4. Limits and trade-offs

- **Thermal stability**: a smaller cell shrinks $K_u V$, eventually
  losing the data to thermal noise. Practical cells need
  $K_u V \gtrsim 60\,k_B T$ for a 10-year retention.
- **Write current**: STT writing requires $J \sim 10^6$–$10^8$ A/cm$^2$
  through the (high-resistance) tunnel barrier, which must be thin
  enough not to break down.
- **Read-disturb**: read currents must be safely below the switching
  threshold to avoid accidentally flipping the bit.

The compromise between read signal, write current, retention, and
barrier reliability is what makes MTJ engineering a multi-decade
research field.

## Summary

An MTJ is two ferromagnets separated by a thin insulator. Spin-conserving
tunneling makes its resistance depend on the relative orientation of
the two magnetizations:

$$
\mathrm{TMR} \;=\; \frac{R_{\text{AP}} - R_{\text{P}}}{R_{\text{P}}}
\;=\; \frac{2 P_1 P_2}{1 - P_1 P_2}.
$$

In crystalline MgO MTJs, symmetry filtering pushes TMR above 600 % at
room temperature. The MTJ has become the storage element of
**STT-MRAM**, a non-volatile, fast, high-endurance memory that is
already a billion-dollar industry and the most likely successor to
embedded SRAM/Flash.

## Connections

- [[spin-valve]] — metallic predecessor of the MTJ; lower MR ratios
- [[spin-polarized-current]] — the $P_1, P_2$ that enter Jullière
- [[spin-transfer-torque]] — how MRAM cells are written
- [[stoner-model]] — the asymmetric DOS that ultimately produces TMR
- [[hysteresis]] — the bistable free-layer loop that stores the bit

## References

- M. Jullière, *Phys. Lett. A* **54**, 225 (1975).
- S. S. P. Parkin et al., *Nat. Mater.* **3**, 862 (2004) — MgO MTJ.
- S. Yuasa et al., *Nat. Mater.* **3**, 868 (2004) — MgO MTJ.
- A. D. Kent & D. C. Worledge, *Nat. Nanotechnol.* **10**, 187 (2015) — STT-MRAM review.
