---
title: "Magnetic Materials"
date: 2026-05-16
tags: [micromagnetism, foundations, diamagnetism, paramagnetism, susceptibility]
description: "Classifying materials by the sign and origin of their magnetic susceptibility: diamagnetic (χ<0), paramagnetic (χ>0, no order), ferromagnetic (χ→∞ at the Curie point)."
---

## Intuition

Place any material in an external magnetic field and ask: which way does
its [[magnetization]] point, and how strong is it? The answer divides every
material into one of three families.

- **Diamagnets** push back gently — their induced magnetization points
  *against* the field. Every material does this, but in most cases the
  effect is so small you'd never notice.
- **Paramagnets** have permanent atomic moments that *don't* talk to each
  other; an external field nudges them into partial alignment, producing a
  weak magnetization parallel to the field.
- **Ferromagnets** have permanent atomic moments that *do* talk to each
  other (via the exchange interaction); below a critical temperature they
  align spontaneously, with or without an applied field, and the rest of
  this wiki is devoted to their physics.

The single dimensionless number that distinguishes them is the **magnetic
susceptibility** $\chi$ — the slope of $\vec{M}$ vs $\vec{H}$ in the
linear-response regime.

## Formal Definition

In the linear-response regime,

$$
\vec{M} \;=\; \chi\,\vec{H},
\qquad
\mu_r \;=\; 1 + \chi.
$$

The magnitude and sign of $\chi$ define the three families:

| Family | Sign of $\chi$ | Typical magnitude | Spontaneous $M$? | Microscopic origin | Examples |
| ------ | -------------- | ----------------- | --------------- | ------------------ | -------- |
| Diamagnetic | $\chi < 0$ | $\sim -10^{-5}$ | no | Lenz response of paired electron orbits | Cu, Bi, water, superconductors ($\chi = -1$) |
| Paramagnetic | $\chi > 0$ | $10^{-5}$–$10^{-3}$ | no | Unpaired atomic moments, randomized by $k_B T$ | Al, Pt, rare-earth salts |
| Ferromagnetic | effective $\chi \gg 1$ | $\to\infty$ at $T = T_C$ | **yes** ($T<T_C$) | Exchange-locked parallel moments | Fe, Co, Ni, Gd, alloys |
| Antiferromagnetic | $\chi > 0$, small | weak | no (compensated) | Exchange-locked antiparallel moments | Cr, MnO, NiO |
| Ferrimagnetic | effective $\chi \gg 1$ | strong | **yes** ($T<T_C$) | Antiparallel **unequal** sub-lattices | Magnetite Fe$_3$O$_4$, ferrites |

The **sign** of $\chi$ already separates the diamagnets (negative) from
everything else; the presence or absence of **spontaneous
magnetization** then separates the ordered families (ferro / ferri)
from the disordered ones (para / antiferro).

## Key Results

### 1. Diamagnetism — universal and Lenz-like

When an external field $\vec{B}$ is turned on, it slightly **deforms** the
orbital motion of bound electrons. By Lenz's law, the induced orbital
current generates a magnetic moment that **opposes** the applied field,
so $\chi_{\text{dia}} < 0$.

Two facts to keep in mind:

- **Every material is diamagnetic.** The orbital response exists for any
  bound electron and gives a small negative $\chi$ that is always present.
  In materials with unpaired spins (paramagnets, ferromagnets) it is
  swamped by larger paramagnetic or ferromagnetic contributions and
  effectively hidden.
- A diamagnet has **mostly paired electrons** in its outer shells — no
  permanent atomic moment to align with the field.

The extreme limit is a **superconductor**, which expels the field entirely
(Meissner effect): $\chi = -1$, $\mu_r = 0$ — perfect diamagnetism.

### 2. Paramagnetism — permanent moments, no order

A **paramagnetic** solid contains atoms with permanent magnetic moments
(unpaired electrons in incomplete shells), but the moments do *not*
interact strongly with one another. In zero applied field, thermal
agitation randomizes their orientations and the macroscopic magnetization
averages to zero.

A field $\vec{H}$ creates a partial alignment, giving a small positive
$\chi$. Two physical regimes — and two laws for $\chi$ — coexist:

**Curie paramagnetism (localized moments)**

For *localized* atomic moments (e.g. rare-earth ions in an insulator),
balancing Zeeman energy against $k_B T$ gives the **Curie law**:

$$
\chi_{\text{Curie}}(T) \;=\; \frac{C}{T},
\qquad C = \frac{n\,\mu_0\,\mu_{\text{eff}}^2}{3 k_B},
$$

where $n$ is the moment density and $\mu_{\text{eff}}$ the effective
atomic moment. The susceptibility diverges as $T\to 0$ — moments freeze
into alignment.

**Pauli paramagnetism (itinerant electrons)**

The Curie law predicts $\chi \propto 1/T$ for *any* metal with permanent
moments — and would give susceptibilities $\sim 10^{-3}$ at room
temperature. **Experiment**, however, finds normal metals to have
$\chi \approx 10^{-5}$, roughly *one hundred times smaller* than Curie
predicts, and essentially **independent of temperature**. The
resolution, due to Pauli (1927), is a purely quantum-statistical effect:
conduction electrons form a **degenerate Fermi gas**, and only a thin
shell of states within $\sim k_B T$ of the Fermi level can actually
respond to a field. The rest are blocked by the [[stoner-model|exclusion
principle]].

The derivation goes through the **rigid-band picture**. Without a
field, the two spin sub-bands have equal DOS $g_\uparrow = g_\downarrow = g(\varepsilon)/2$.
A Zeeman shift $\pm\mu_B B$ moves them in opposite directions; refilling
to a common Fermi level transfers $\Delta N \approx g(\varepsilon_F)\mu_B B/2$
electrons from spin-↓ to spin-↑. The net magnetization is
$M = \mu_B(N_\uparrow - N_\downarrow)/V$ and yields

$$
\boxed{\;\chi_{\text{Pauli}} \;=\; \mu_0\,\mu_B^2\,g(\varepsilon_F)/V.\;}
$$

Comparison to the Curie law makes the physics quantitative. For the
same number of electrons,

$$
\frac{\chi_{\text{Pauli}}}{\chi_{\text{Curie}}} \;\approx\; \frac{T}{T_F} \;\approx\; \frac{300\,\text{K}}{10^4\,\text{K}} \;\approx\; 10^{-2},
$$

— i.e. **only a fraction $T/T_F$ of the electrons are thermally
active**; the rest are frozen by Pauli. Pauli paramagnetism is the
dominant magnetic response of "ordinary" metals (Na, Al, Cu), partially
cancelled by their orbital diamagnetism. It also provides a direct
experimental window on $g(\varepsilon_F)$ — the **band structure** of
a metal can be probed by measuring its susceptibility. Pauli enhanced
to within a hair of instability is precisely the regime of the
[[stoner-model|Stoner criterion]].

### 3. Ferromagnetism — exchange wins over $k_B T$

In a ferromagnet, the [[micromagnetic-energy|exchange interaction]] makes
neighboring atomic moments prefer to align *with each other*, independent
of any external field. Below the **Curie temperature** $T_C$ the alignment
sets in spontaneously, producing the [[magnetic-domains|domain structure]]
that the rest of this wiki is built on.

The susceptibility diverges at $T_C$ (**Curie–Weiss law**):

$$
\chi(T) \;=\; \frac{C}{T - T_C}, \qquad T > T_C.
$$

The shift from Curie ($1/T$) to Curie–Weiss ($1/(T-T_C)$) is the
fingerprint of the exchange interaction: at $T = T_C$ the inverse
susceptibility extrapolates to zero, which is the signature of a
**second-order phase transition** to a spontaneously magnetized state.
The Curie temperatures of the elemental ferromagnets are large by
microscopic standards — far above what dipole–dipole interactions
could ever produce, requiring the much stronger
[[micromagnetic-energy#exchange|exchange interaction]]:

| Element | $T_C$ (K) | $\mu_{\text{atom}}\;(\mu_B)$ | $\mu_0 M_s$ (T) |
| ------- | --------- | ---------------------------- | ---------------- |
| Fe (bcc) | 1043 | 2.22 | 2.15 |
| Co (hcp) | 1388 | 1.72 | 1.80 |
| Ni (fcc) | 627 | 0.61 | 0.64 |
| Gd (hcp) | 292 | 7.55 | 2.49 |

The non-integer atomic moments of Fe, Co, Ni are themselves a window
on **itinerant magnetism** — see [[stoner-model]] for why they cannot
be explained by localized spins. Below $T_C$ the response becomes
**nonlinear** and **hysteretic**:
$\chi$ ceases to be a meaningful single-valued number, and one switches
to the language of [[magnetization|magnetization curves]],
[[magnetic-domains|domain walls]], and [[llg-equation|dynamics]].

## Summary

A material's magnetic class is fixed by *what its atoms look like* and by
*how strongly the atoms talk to each other*:

- **No unpaired spins** → only the Lenz response remains → **diamagnetic**.
- **Unpaired spins, weakly interacting** → field-driven partial
  alignment → **paramagnetic** (Curie for localized, Pauli for itinerant).
- **Unpaired spins, strongly exchange-coupled** → spontaneous alignment
  below $T_C$ → **ferromagnetic** (the subject of micromagnetism).

## Connections

- [[magnetization]] — defines $\vec{M}$, $\chi$, $\mu_r$
- [[magnetic-atom]] — paired vs unpaired electrons; sets the available family
- [[magnetic-moment]] — the atomic-scale building block
- [[micromagnetic-energy]] — exchange, the term that turns a paramagnet into a ferromagnet
- [[magnetic-domains]] — what spontaneous order looks like in a ferromagnet

## References

- S. Blundell, *Magnetism in Condensed Matter* (Oxford, 2001), Chs. 1–3.
- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Chs. 4–5.
- N. W. Ashcroft & N. D. Mermin, *Solid State Physics*, Ch. 31 — Pauli paramagnetism.
