---
title: "Stoner Model"
date: 2026-05-16
tags: [micromagnetism, ferromagnetism, stoner, band-magnetism, dft]
description: "Band-theory picture of ferromagnetism in 3d metals: spin-split bands, the Stoner criterion I·g(εF) > 1, and why Fe/Co/Ni alone among the elements are ferromagnetic at room temperature."
---

## Intuition

The Heisenberg picture of ferromagnetism — fixed atomic moments coupled
by exchange — works beautifully for **insulating** magnets like the rare
earths or magnetic oxides. But it fails in an embarrassing way for the
3d transition metals that everyone actually uses:

- Iron carries $\mu_{\text{atom}} \approx 2.22\,\mu_B$ per atom — **not an integer**.
- Nickel carries $\mu_{\text{atom}} \approx 0.61\,\mu_B$ per atom — much less than one Bohr magneton.

Localized spins on an atom can only give integer (or half-integer)
moments, so something else is going on. The resolution, due to Stoner
(1938), is that the magnetism of the 3d metals lives in the **band
electrons** themselves: the same electrons that carry the current also
carry the magnetization. They are **itinerant**, not localized.

The mechanism is then geometric: the exchange interaction pushes up one
spin band and pulls down the other; the bands fill up to a common Fermi
level, and the difference in occupation is the magnetization. Whether
this self-consistent splitting is energetically favourable is decided
by a single number — the **Stoner criterion**.

## Formal definition

Take a paramagnetic metal with a single density of states $g(\varepsilon)$
per spin in zero field, so that $g_\uparrow(\varepsilon) = g_\downarrow(\varepsilon) = g(\varepsilon)/2$.
The Stoner ansatz assumes the two spin sub-bands remain rigid but are
**shifted in energy** by an internal molecular field proportional to the
magnetization itself:

$$
\varepsilon_\uparrow(\vec{k}) \;=\; \varepsilon(\vec{k}) - I\,m,
\qquad
\varepsilon_\downarrow(\vec{k}) \;=\; \varepsilon(\vec{k}) + I\,m,
$$

where
$m = (n_\uparrow - n_\downarrow)/n$ is the dimensionless reduced
magnetization and $I$ is the **Stoner parameter** — the exchange energy
per pair of electrons of the same spin, a material constant of order
$0.5$–$1$ eV in the 3d metals.

## Key results

### 1. Band picture of a ferromagnet

Imagine the paramagnetic DOS $g(\varepsilon)$ filled up to a common
Fermi level $\varepsilon_F$. Turn on the exchange splitting $2Im$:

1. The spin-↑ band slides **down** by $Im$ — it gains electrons.
2. The spin-↓ band slides **up** by $Im$ — it loses electrons.
3. The net imbalance $n_\uparrow - n_\downarrow$ is the magnetization.

Because the bands are continuous, the resulting moment per atom is in
general **non-integer** — exactly what is observed in Fe, Co, Ni.
Nickel is the textbook case: the majority d-band is completely filled,
the minority d-band has $\approx 0.6$ holes per atom, and the magnetic
moment is $\mu \approx 0.6\,\mu_B$.

### 2. The Stoner criterion

Whether the spin-split solution is energetically favourable comes from
a competition at the Fermi level. Move a small slice $\delta n$ of
electrons from spin-↓ to spin-↑:

- **Kinetic cost** (Pauli-like): promoting electrons across the Fermi
  level costs
  $$
  \Delta E_{\text{kin}} \;\approx\; \frac{(\delta n)^2}{g(\varepsilon_F)}.
  $$
- **Exchange gain**: the same spin imbalance lowers the exchange energy
  by
  $$
  \Delta E_{\text{ex}} \;\approx\; -I\,(\delta n)^2.
  $$

A spontaneous magnetization appears precisely when the gain beats the
cost, i.e. when

$$
\boxed{\;I \cdot g(\varepsilon_F) \;>\; 1\;}\qquad\text{(Stoner criterion)}.
$$

The criterion favours metals with a **large density of states at the
Fermi level**, which is exactly what narrow, partially filled d-bands
deliver. This is why ferromagnetism at room temperature is the privilege
of a handful of 3d transition metals (Fe, Co, Ni) and not the noble
metals (Cu, Ag, Au), whose Fermi level sits in a broad, dilute s-band.

### 3. Pd: the textbook near-miss

Palladium has $I \cdot g(\varepsilon_F) \approx 0.9$ — just below the
threshold. It is **not** ferromagnetic, but its [[magnetic-materials|Pauli
susceptibility]] is enormously enhanced ($\chi \sim 10^{-3}$, two orders
of magnitude above an ordinary metal). A small impurity of Fe or Co can
push it over the edge — Pd is on the brink of ferromagnetism.

### 4. Non-integer moments, explained

The non-integer atomic moments of Fe, Co, Ni follow from the rigid-band
picture above:

| Element | $\mu_{\text{atom}}\;(\mu_B)$ | Band picture |
| ------- | --------------------------- | ------------ |
| Fe (bcc) | $2.22$ | both d-bands partially filled |
| Co (hcp) | $1.72$ | majority filled, minority partially filled |
| Ni (fcc) | $0.61$ | majority filled, $\approx 0.6$ minority holes |

There are no whole spins to count — only a continuous Fermi-level
imbalance between two spin populations.

## Limits and refinements

- The Stoner model overestimates $T_C$ because it ignores **spin-wave
  excitations** (magnons), which are the cheap low-temperature
  excitations that actually destroy long-range order. Modern theory
  combines Stoner physics with Heisenberg-like spin fluctuations.
- It also predicts only a smooth, mean-field transition; the true
  ferromagnetic transition is second-order with critical fluctuations.
- For rare-earth ferromagnets (Gd, Dy, …), the 4f electrons *are*
  localized and the **Heisenberg model** is the right starting point;
  the Stoner picture is reserved for the 3d itinerant magnets.

## Summary

Stoner replaced the picture of localized atomic moments by a picture
of **spin-polarized bands**: the same electrons that carry the current
carry the magnetization. The transition to ferromagnetism is set by a
single dimensionless number,

$$
I \cdot g(\varepsilon_F) \;>\; 1,
$$

which is satisfied only by the 3d transition metals Fe, Co, Ni. The
non-integer atomic moments measured in those metals are a direct
fingerprint of itinerant magnetism.

## Connections

- [[magnetic-materials]] — Pauli paramagnetism (the $I = 0$ limit of Stoner)
- [[magnetic-moment]] — the Bohr magneton and the meaning of $\mu_{\text{atom}}$
- [[micromagnetic-energy]] — Heisenberg exchange, the localized counterpart
- [[magnetocrystalline-anisotropy]] — spin-orbit coupling on top of the band picture
- [[hysteresis]] — what a ferromagnet does once it exists

## References

- E. C. Stoner, *Proc. Roy. Soc. A* **165**, 372 (1938).
- S. Blundell, *Magnetism in Condensed Matter* (Oxford, 2001), Ch. 7.
- J. Kübler, *Theory of Itinerant Electron Magnetism* (Oxford, 2009).
