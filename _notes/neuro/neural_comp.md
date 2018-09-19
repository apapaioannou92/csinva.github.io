---
layout: notes
section-type: notes
title: comp neuro 2
category: neuro
---

* TOC
{:toc}
---

- website: from redwood website

# introduction

## overview

- does biology have a cutoff level (likecutoffs in computers below which fluctuations don't matter)
- core principles underlying these two questions
  - how do brains work?
  - how do you build an intelligent machine?
- lacking: insight from neuro that can help build machine
- scales: cortex, column, neuron, synapses
- physics: theory and practice are much closer
- are there principles?
  - "god is a hacker" - francis crick
  - theorists are lazy - ramon y cajal
  - things seemed like mush but became more clear - horace barlow
  - principles of neural design book
- felleman & van essen 1991
  - ascending layers (e.g. v1-> v2): goes from superficial to deep layers
  - descending layers (e.g. v2 -> v1): deep layers to superficial
- **solari & stoner 2011 "cognitive consilience"** - layers thicknesses change in different parts of the brain
  - motor cortex has much smaller input (layer 4), since it is mostly output

## historical ai

- people: turing, von neumman, marvin minsky, mccarthy...
- ai: birth at 1956 conference
  - vision: marvin minsky thought it would be a summer project
- lighthill debate 1973 - was ai worth funding?
- intelligence tends to be developed by young children...
- cortex grew very rapidly

## historical cybernetics/nns

- people: norbert weiner, mcculloch & pitts, rosenblatt
- neuro
  - hubel & weisel (1962, 1965) simple, complex, hypercomplex cells
  - neocognitron fukushima 1980
  - david marr: theory, representation, implementation

# neuron models

## circuit-modelling basics

- membrane has capacitance $C_m$
- force for diffusion, force for drift
- can write down diffeq for this, which yields an equilibrium
- $\tau = RC$
  - bigger $\tau$ is slower
  - to increase capacitance
    - could have larger diameter
    - $C_m \propto D$
  - axial resistance $R_A \propto 1/D^2$ (not same as membrane lerk), thus bigger axons actually charge faster

## action potentials

- channel/receptor types
  - ionotropic: $G_{ion}$ = f(molecules outside)
    - something binds and opens channel
  - metabotropic: $G_{ion}$ = f(molecules inside)
    - doesn't directly open a channel: indirect
  - others
    - photoreceptor
    - hair cell
  - voltage-gated (active - provide gain; might not require active ATP, other channels are all passive)

## physics of computation

- based on carver mead: drift and diffusion are at the heart of everything
- different things realted by the **Boltzmann distr.** (ex. distr of air molecules vs elevation. Subject to gravity and diffusion upwards since they're colliding)
  - nernst potential
  - current-voltage relation of voltage-gated channels
  - current-voltage relation of MOS transistor
- these things are all like transistor: energy barrier that must be overcome
- neuromorphic examples
  - differential pair sigmoid yields sigmoid-like function
    - can compute tanh function really simply to simulate
  - silicon retina
    - lateral inhibition exists (gap junctions in horizontal cells)
    - mead & mahowald 1989 - analog VLSI retina (center-surround receptive field is very low energy)
- computation requires energy (otherwise signals would dissipate)
  - von neumann architecture: CPU - bus (data / address) - Memory
    - moore's law ending (in terms of cost, clock speed, etc.)
      - ex. errors increase as device size decreases (and can't tolerate any errors)
  - neuromorphic computing
    - brain ~ 20 Watts
    - exploit intrinsic transistor physics (need extremely small amounts of current)
    - exploit electronics laws kirchoff's law, ohm's law
    - new materials (ex. memristor - 3d crossbar array)
    - can't just do biological mimicry - need to understand the principles

# supervised learning

- see machine learning course
- net talk was major breakthrough (words -> audio) Sejnowski & Rosenberg 1987
- people looked for world-centric receptive fields (so neurons responded to things not relative to retina but relative to body) but didn't find them
  - however, they did find gain fields: (Zipser & Anderson, 1987)
    - gain changes based on what retina is pointing at
  - trained nn to go from pixels to head-centered coordinate frame
    - yielded gain fields
  - pouget et al. were able to find that this helped having 2 pop vectors: one for retina, one for eye, then add to account for it
- support vector networks (vapnik et al.) - svms early inspired from nns
- dendritic nonlinearities (hausser & mel 03)
- example to think about neurons due this: $u = w_1 x_1 + w_2x_2 + w_{12}x_1x_2$
  - $y=\sigma(u)$
  - somestimes called sigma-pi unit since it's a sum of products
  - exponential number of params...**could be fixed w/ kernel trick?**
    - could also incorporate geometry constraint...

# unsupervised learning

- born w/ extremely strong priors on weights in different areas
- barlow 1961, attneave 1954: efficient coding hypothesis = redundancy reduction hypothesis
  - representation: compression / usefulness
  - easier to store prior probabilities (because inputs are independent)
  - relich 93: redundancy reduction for unsupervised learning (text ex. learns words from text w/out spaces)

## hebbian learning and pca

- pca can also be thought of as a tool for decorrelation (in pc dimension, tends to be less correlated)
- hebbian learning = fire together, wire together: $\Delta w_{ab} \propto <a, b>$ note: $<a, b>$ is correlation of a and b (average over time)
- linear hebbian learning (perceptron with linear output)
- $\dot{w}_i \propto <y, x_i> \propto \sum_j w_j <x_j, x_i>$ since weights change relatively slowly
  - 

# sparse, distributed coding



# self-organizing maps



# manifold learning



# reinforcement learning



# recurrent networks



# probabilistic models + inference



# boltzmann machines



# ica



# dynamical models



# neural coding



# high-dimensional computing
