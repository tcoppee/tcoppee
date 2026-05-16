---
title: "Magnetic Atom"
date: 2026-05-16
tags: [micromagnetism, foundations, atom, electrons, bound-vs-conduction]
description: "What makes an atom magnetic: unpaired electron spins, the role of 3d/4f orbitals, and why magnetism survives an electric current."
---

## Intuition

Not every atom is magnetic. Carbon, oxygen, copper — all "ordinary" atoms —
contain electrons whose spins **pair up** and cancel: each pair carries
opposite spin, contributes zero net [[magnetic-moment|magnetic moment]],
and the atom is magnetically silent. **Magnetic atoms** are the exceptions:
their electron shells contain **unpaired spins** that don't have partners to
cancel against. Iron, cobalt, and nickel are the famous examples — their
**3d** shell hosts several unpaired electrons, and the resulting net moment
is what ultimately makes a fridge magnet stick to a fridge.

A subtle but important point follows: when current flows through a
ferromagnetic wire, the wire **does not demagnetize**. The electrons that
*carry the current* are different from the electrons that *carry the
magnetism*. Sorting these two populations is the conceptual key to
spintronics.

## Formal Definition

An atom is **magnetic** when its electron configuration leaves a non-zero
total electronic angular momentum, so that its [[magnetic-moment|atomic
magnetic moment]] $\boldsymbol{\mu}_{\text{atom}} \neq \vec{0}$.

Equivalently, in the simplest spin-only picture: a magnetic atom is one
with **at least one unpaired electron**.

In a metal, the atom's electrons fall into two populations:

- **Bound (core / localized) electrons** — tied to the nucleus, sitting in
  inner shells (e.g. **3d** in Fe/Co/Ni, **4f** in rare earths). These
  carry the magnetism.
- **Conduction electrons** — delocalized over the lattice (e.g. 4s in Fe);
  they carry the electrical current.

## Key Results

### 1. Origin: unpaired spins in inner shells

In iron (Z = 26), the electronic configuration is

$$
\mathrm{[Ar]}\,3d^6\,4s^2.
$$

By **Hund's first rule**, the 3d electrons maximize total $S$: four of the
six 3d electrons occupy *different* orbitals with parallel spin, leaving
$\sim 4$ unpaired spins per atom and an atomic moment of roughly
$2$–$2.2\,\mu_B$ in metallic Fe. Pair them all up — as happens for C or
O in typical bonds — and the atomic moment vanishes.

The same mechanism is responsible for the magnetic moments of Co, Ni
(**3d** transition metals) and Gd, Dy, etc. (**4f** rare earths).

### 2. Why a current does not erase the magnetism

A common confusion: if "electrons are moving through the wire," why doesn't
the magnetism flow away? Because two different electron populations live
side by side:

- The **bound 3d electrons** stay locked in their atomic shells. The
  nucleus and these inner-shell electrons remain fixed in the lattice
  (they only vibrate thermally), so the atomic [[magnetic-moment|magnetic moment]]
  stays put.
- The **conduction 4s electrons** move through the lattice and carry the
  current. They feel the local exchange field of the bound moments, which
  **polarizes** them and causes **spin-dependent scattering** — the
  microscopic origin of giant magnetoresistance in a
  [[spin-valve|spin valve]] and of the
  [[spin-polarized-current|spin-polarized current]] in spintronics.

This separation of roles — *localized* moments + *itinerant* carriers — is
the **s–d model** of itinerant ferromagnetism, and it is what makes
spintronics work.

## Summary

- An atom is magnetic when **at least one of its electrons is unpaired**
  (typically in a partially filled 3d or 4f shell).
- The magnetism resides in the **bound** electrons, which stay fixed with
  the nucleus in the lattice.
- The current is carried by the **conduction** electrons, which are
  spin-polarized by the bound moments but never erase them.
- Therefore a ferromagnet can simultaneously be a magnet *and* a conductor —
  the prerequisite for every spintronic device.

## Connections

- [[magnetic-moment]] — the vector quantifying the atomic magnetism
- [[magnetization]] — collective field built from atomic moments
- [[spin]] — intrinsic angular momentum of the electron *(stub)*
- [[spin-polarized-current]] — current shaped by the bound moments *(stub)*
- [[spin-valve]] — device exploiting spin-dependent scattering

## References

- J. M. D. Coey, *Magnetism and Magnetic Materials* (Cambridge, 2010), Ch. 3–4.
- N. W. Ashcroft & N. D. Mermin, *Solid State Physics*, Ch. 31–32.
- S. Blundell, *Magnetism in Condensed Matter* (Oxford, 2001).
