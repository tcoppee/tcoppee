---
title: "Superconductivity"
date: 2026-05-16
tags: [superconductivity, meissner, bcs, cooper-pair, type-i, type-ii, flux-quantization]
description: "From Onnes (1911) to BCS to MRI, LHC, and SQUIDs: the three universal signatures, Type I vs Type II, Cooper pairs, the BCS gap, and the big applications."
---

## Intuition

In 1911, Heike Kamerlingh Onnes — just three years after liquefying
helium — measured the resistivity of pure mercury below 4.2 K and
watched it drop **abruptly to zero**. The result wasn't a "very good
conductor"; it was a **new state of matter**, qualitatively different
from a normal metal, in which the electrical properties of the
material change in three universal ways:

1. **Zero DC resistivity** — currents persist for years without
   attenuation.
2. **Perfect diamagnetism** (Meissner–Ochsenfeld, 1933) — the field is
   *expelled* from the volume, not merely frozen out.
3. **Magnetic flux quantization** — the flux through a superconducting
   loop is an integer multiple of $\Phi_0 = h/(2e) \approx 2.07\times 10^{-15}$ Wb.

The three signatures are inseparable: each is a different face of a
single macroscopic quantum wavefunction, **Bose-condensed pairs of
electrons** (BCS, 1957). This page is the entry point for the
superconductivity half of the wiki — the magnetic-material analogue
of [[index|the rest]] of this site.

## Formal definition

A material is **superconducting** below a critical temperature $T_C$,
critical magnetic field $H_C$ (or $H_{C2}$ for Type II), and critical
current density $J_C$. The state survives only inside the
three-parameter envelope $T < T_C$, $H < H_C$, $J < J_C$; exceed any
one and the sample suddenly returns to the normal state — a **quench**.

The thermodynamic order parameter is a **complex macroscopic
wavefunction** $\psi(\vec{r}) = \sqrt{n_s}\,e^{i\phi(\vec{r})}$
describing the density and phase of the superconducting condensate
($n_s$ = density of paired electrons).

## Key results

### 1. Three universal signatures

**(a) Zero DC resistivity ($\rho = 0$).** Currents in a superconducting
ring decay with time constants measured in years. Joule loss
$P = R I^2 = 0$ — perfect lossless transport. This is genuinely
different from a "very pure" metal, where $\rho$ tends to a finite
*residual* resistivity as $T \to 0$; in a superconductor the
transition at $T_C$ is **abrupt**.

**(b) Meissner effect ($\chi_V = -1$).** Below $T_C$ a superconductor
**expels** the magnetic field from its interior: $\vec{B} = 0$ inside,
not by induction but as an equilibrium property. The field penetrates
only over a thin surface layer of depth

$$
\lambda \;=\; \sqrt{\frac{m_e}{\mu_0\,n_s\,e^2}} \;\sim\; 50\text{–}500\ \text{nm}
$$

— the **London penetration depth**. The Meissner effect is what allows
a magnet to **levitate** over a cooled superconductor; it is *not* the
same as "$\rho = 0$" — a hypothetical perfect conductor would *trap*
whatever field was present when it became conductive, whereas a
superconductor expels it.

**(c) Flux quantization.** The magnetic flux through a closed
superconducting loop is

$$
\Phi \;=\; n\,\Phi_0, \qquad \Phi_0 \;=\; \frac{h}{2e} \;\approx\; 2.07\times 10^{-15}\ \text{Wb}.
$$

The integer $n$ and the factor **$2e$** (not $e$) are both direct
proofs of the **Cooper-pair** character of the condensate. This effect
is exploited by **SQUIDs** — sensors that can detect $10^{-14}$ T
fields, used in biomagnetism (brain, heart) and geomagnetism.

### 2. Critical parameters and the phase diagram

The three critical parameters bound a phase diagram in
$(T, H, J)$-space inside which superconductivity is stable:

$$
H_C(T) \;\approx\; H_C(0)\,\Big[\,1 - (T/T_C)^2\,\Big].
$$

Exceeding any boundary triggers a **quench** — local heating from
$\rho > 0$ further raises $T$, propagating the normal region. Quench
protection (resistive bypasses, cold reservoirs) is half the
engineering effort of any superconducting magnet.

### 3. Type I vs Type II

| | **Type I** | **Type II** |
| --- | -------- | --------- |
| Critical fields | one $H_C$, abrupt transition | $H_{C1} < H_{C2}$, mixed state in between |
| $H_{C2}$ | n/a | up to $> 50$ T |
| Mixed state | none | **Abrikosov vortex lattice** |
| Ginzburg–Landau ratio | $\kappa = \lambda/\xi < 1/\sqrt{2}$ | $\kappa > 1/\sqrt{2}$ |
| Materials | pure elements: Hg, Pb, Sn, Al | alloys & compounds: Nb-Ti, Nb$_3$Sn, cuprates |
| Used for | almost nothing practical | every real superconducting magnet |

The criterion ($\kappa$ above or below $1/\sqrt{2}$) is the sign of
the **surface energy** between a superconducting and normal region:
positive in Type I (interfaces cost energy → field stays out), negative
in Type II (interfaces *lower* the energy → field penetrates as a lattice
of tubes).

### 4. Abrikosov vortices

In the mixed state of Type II ($H_{C1} < H < H_{C2}$), the magnetic
field penetrates as a triangular lattice of **flux tubes**, each
carrying exactly **one flux quantum $\Phi_0$**. Each vortex has a
normal-state **core** of radius $\xi$ (coherence length), surrounded
by circulating supercurrents on a scale $\lambda$.

A flowing current exerts a **Lorentz force** $\vec{J}\times\vec{\Phi}_0$
on each vortex; if vortices move, they dissipate, and $\rho > 0$
returns. The industrial trick is to **pin** vortices on engineered
defects (nano-precipitates, dislocations), raising the effective $J_C$
by orders of magnitude. This **flux-pinning engineering** is what makes
Nb-Ti, Nb$_3$Sn and YBCO wires actually useful in magnets.

### 5. BCS theory and Cooper pairs (1957)

The mechanism that condenses the electrons into pairs is, somewhat
miraculously, an **attractive interaction mediated by the lattice
vibrations (phonons)**:

1. An electron polarizes the positive ion background as it moves.
2. A second electron is weakly attracted to that polarization wake.
3. The attraction binds a **Cooper pair** of opposite momenta and
   opposite spins (a spin singlet, total spin 0).
4. Pairs are **bosons** and Bose-condense into a single macroscopic
   wavefunction.

The pair has charge $-2e$ — the famous factor that appears in
$\Phi_0$. The condensate sits below an **energy gap** $\Delta(T)$ at
the Fermi level:

$$
2\Delta(0) \;\approx\; 3.52\,k_B T_C \quad\text{(BCS, weak coupling)}.
$$

Excitations cost at least $2\Delta$ — the energy to break one pair.
That gap protects the condensate from dissipation: as long as
$k_B T \ll \Delta$, almost no quasi-particles are excited, and the
transport is lossless.

**Experimental fingerprint:** the **isotope effect** $T_C \propto M^{-1/2}$
(Maxwell & Reynolds, 1950) — replacing $^{200}$Hg by $^{204}$Hg shifts
$T_C$ exactly as predicted by phonon mediation. This was the smoking
gun that pointed to BCS.

### 6. Material families

| Family | Example $T_C$ | Notes |
| ------ | ------------ | ----- |
| Elemental "low-$T_C$" | Hg (4.2 K), Pb (7.2 K), Al (1.2 K) | Type I, historical |
| Metallic alloys | Nb-Ti (9.2 K), Nb$_3$Sn (18 K) | **industry workhorse** (LHC, MRI) |
| Cuprates "high-$T_C$" | YBa$_2$Cu$_3$O$_7$ (93 K), Bi-2223 (110 K), HgBaCaCuO (138 K) | above the 77 K barrier — liquid-N$_2$ cooling |
| Iron pnictides | LaFeAsO (since 2008), FeSe | mechanism still debated |
| Hydrides under pressure | H$_3$S (203 K), LaH$_{10}$ ($\sim$250 K!) | only at hundreds of GPa |

The **room-temperature superconductor at ambient pressure** remains
the holy grail; if found it would revolutionize electronics, energy
transport, and magnetic levitation.

## Why we use superconductors

Industrial and scientific uses cluster around what only a
superconductor can deliver:

- **Very high magnetic fields in a small volume** → MRI (1.5–7 T),
  NMR spectrometers.
- **High current density without DC losses** → power transmission
  cables (AmpaCity Essen, Long Island).
- **Extreme stability and precision** → LHC (1232 Nb-Ti dipoles at 8 T),
  ITER toroidal field coils (Nb$_3$Sn).
- **Ultra-sensitive detection** → SQUIDs, bolometers.
- **Platform for quantum bits** → superconducting transmons (IBM,
  Google, Rigetti).

The trade-off is cryogenics: superconductors must be cooled, and a
*quench* dumps stored magnetic energy as heat. The choice is justified
only when no normal-metal solution can match the required field, current,
or sensitivity.

## Summary

Superconductivity is a macroscopic quantum state — Cooper pairs
condensed below a critical temperature. Three inseparable signatures:

- $\rho = 0$ (zero DC resistivity),
- the Meissner effect (perfect diamagnetism, $\chi_V = -1$),
- $\Phi = n\,\Phi_0$ flux quantization with $\Phi_0 = h/(2e)$.

A three-parameter phase diagram $(T_C, H_C, J_C)$ bounds the
superconducting state. **Type I** materials transition abruptly at
$H_C$; **Type II** materials admit a mixed state of Abrikosov vortices
between $H_{C1}$ and $H_{C2}$, and they are what every working magnet
is actually made of. **BCS theory** explains the lot through
phonon-mediated Cooper pairing and an energy gap
$2\Delta(0) \approx 3.52\,k_B T_C$.

The applications that justify the cryogenics — MRI, LHC, ITER, SQUIDs,
quantum computing — are all built on the same three signatures.

## Connections

- [[magnetic-materials]] — superconductors are extreme diamagnets ($\chi = -1$)
- [[stoner-model]] — both are gap-opening instabilities of the Fermi sea, but with opposite spin character
- [[micromagnetic-energy]] — the supercurrent expelling flux is the analogue of magnetostatic flux closure

## References

- M. Tinkham, *Introduction to Superconductivity*, 2nd ed. (Dover, 2004).
- J. R. Schrieffer, *Theory of Superconductivity* (Westview, 1999).
- P. G. de Gennes, *Superconductivity of Metals and Alloys* (Westview, 1999).
- J. F. Annett, *Superconductivity, Superfluids and Condensates* (Oxford, 2004).
