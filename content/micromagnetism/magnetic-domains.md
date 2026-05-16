---
title: "Magnetic Domains"
date: 2026-05-16
tags: [micromagnetism, domains, domain-walls, hysteresis]
description: "Why ferromagnets break into domains, what separates them, and how an external field reshapes the domain pattern."
---

## Intuition

If every spin in a bar of iron pointed the same way, the bar would behave
like a giant magnet — and pay a huge energetic price in the **stray field**
filling the room around it. Nature avoids the bill by splitting the material
into **domains**: regions of uniform magnetization pointing in *different*
directions, arranged so the flux loops back inside the sample and almost
nothing leaks out. The price of doing this is the **domain wall** — a thin
transition layer where the magnetization gradually rotates from one domain's
direction to another. The equilibrium domain pattern is the one that
minimizes the *sum* of stray-field energy and wall energy.

## Formal Definition

A **magnetic domain** is a spatial region where the magnetization is nearly
uniform along one of the material's [[micromagnetic-energy|easy axes]]:

$$
\vec{M}(\vec{r}) \simeq M_s\,\hat{e}_i \qquad \text{(inside domain $i$)}.
$$

A **domain wall** is the continuous transition between two neighboring
domains, with width $\delta$ set by the balance between the local exchange
and anisotropy terms of the [[micromagnetic-energy|total energy functional]]:

$$
\delta \;\simeq\; \pi\sqrt{\frac{A}{K}},
$$

where $A$ is the exchange stiffness (J/m) and $K$ the anisotropy constant
(J/m³). The associated **wall energy per unit area** is

$$
\sigma_{\text{w}} \;\simeq\; 4\sqrt{A\,K}.
$$

## Key Results

### 1. Why domains exist

A uniformly magnetized body generates a stray field $\vec{H}^{\text{ms}}$
outside (and a demagnetizing field inside), contributing the
**magnetostatic energy** $W^{\text{ms}}$ of the
[[micromagnetic-energy|total energy]]. By splitting into oppositely
magnetized domains, the flux short-circuits *inside* the material and
$W^{\text{ms}}$ drops dramatically.

The cost is the introduction of **walls**. The equilibrium domain count is
the compromise:

- Too few domains → large $W^{\text{ms}}$.
- Too many domains → large total wall area, large wall energy.

For a slab of thickness $t$, Kittel's classic estimate gives a domain
period $D \propto \sqrt{\sigma_{\text{w}}\,t / (\mu_0 M_s^2)}$.

### 2. Structure of a domain wall

Inside a wall, $\vec{m}$ rotates continuously. The two canonical wall types
differ in *how* it rotates relative to the wall plane:

- **Bloch wall:** $\vec{m}$ rotates **out of** the wall plane. Favored in
  thick bulk samples.
- **Néel wall:** $\vec{m}$ rotates **within** the wall plane. Favored in
  thin films, where Bloch walls would create surface charges and pay a
  large magnetostatic cost.

Both widths scale as $\sqrt{A/K}$; the choice between them is set by sample
geometry through $W^{\text{ms}}$.

### 3. Energy balance summary

| Energy term | Physical meaning | Effect on domain structure |
| ----------- | ---------------- | -------------------------- |
| Exchange | Favors uniform alignment of neighboring spins | Sets wall width (wants wide walls) |
| Anisotropy | Favors easy-axis alignment | Sets wall width (wants narrow walls) and the domain axes |
| Magnetostatic | Penalizes stray field | **Drives** domain formation |
| Wall energy | Cost of each wall ($\sim 4\sqrt{AK}$ per unit area) | **Limits** the number of domains |
| Zeeman | Coupling to $\vec{H}^{\text{ext}}$ | Drives wall motion and rotation |

### 4. Response to an external field — and hysteresis

When an external field $\vec{H}^{\text{ext}}$ is applied:

1. **Wall motion:** domains favorably aligned with $\vec{H}^{\text{ext}}$
   **grow**; opposite domains **shrink**.
2. **Rotation:** at higher fields, residual misalignment within domains is
   removed by coherent rotation of $\vec{m}$ toward the field.
3. **Saturation:** above the saturation field, the sample is a single
   domain along $\vec{H}^{\text{ext}}$.

Pinning of walls on defects, grain boundaries, and inclusions prevents the
domain pattern from fully reversing when the field is removed — this is
the microscopic origin of [[hysteresis|magnetic hysteresis]].

<!-- TODO: add diagram (magnetic_domain.png) illustrating domain pattern and wall structure -->

## Summary

| Concept | Description |
| ------- | ----------- |
| **Magnetic domain** | Region of uniform magnetization along an easy axis |
| **Domain wall** | Continuous transition between two domains ($\delta \sim \pi\sqrt{A/K}$) |
| **Bloch vs Néel** | Out-of-plane vs in-plane rotation; geometry-dependent |
| **Why domains form** | To reduce $W^{\text{ms}}$ via internal flux closure |
| **Equilibrium pattern** | Compromise between $W^{\text{ms}}$ and total wall energy |

## Connections

- [[micromagnetic-energy]] — the four energies whose balance produces domains
- [[llg-equation]] — dynamics of wall motion under field or current
- [[hysteresis]] — irreversibility from wall pinning *(stub)*
- [[exchange-interaction]] — sets $A$, the wall-width numerator *(stub)*
- [[magnetocrystalline-anisotropy]] — sets $K$, the wall-width denominator *(stub)*

## References

- C. Kittel, *Rev. Mod. Phys.* **21**, 541 (1949) — domain theory.
- A. Hubert & R. Schäfer, *Magnetic Domains* (Springer, 1998).
- S. Chikazumi, *Physics of Ferromagnetism* (Oxford, 1997).
