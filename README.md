# GaiaBasic

**A Python library and world-description language for simulating metaphysical theories of consciousness, sentience and identity.**

Website: [gaiabasic.com](https://gaiabasic.com/) · Research: [sentience-research.org](https://sentience-research.org/)

> **Status: design phase.** The concepts are defined and the API is being designed. Code will appear in this repository soon. Names and signatures in this README may change.

## What is GaiaBasic?

We don't know which beings can feel, how much they feel, or why. Theories of consciousness are usually argued in prose, and prose hides contradictions.

GaiaBasic lets you build a simulated world whose basic components reflect a chosen philosophical theory:

- **Substance:** how many kinds of thing exist: monism, dualism, trialism, quadrialism…
- **Sentience:** where experience comes from and what it does: emergentism, immersionism, panpsychism, functionalism, eliminativism, epiphenomenalism…
- **Identity:** who has each experience: closed, empty or open individualism.

You then run the world and measure its coherence, its evolutionary viability, its fit with observations, and how much pleasure and suffering it contains.

GaiaBasic simulates *theories about* sentience. It does not create sentience, and it does not try to test whether we live in a simulation.

## Basic elements

| Element | Includes |
|---|---|
| Information | Matter |
| Ideas | Mathematics |
| Consciousness | Sentience (experiences with positive or negative valence) |
| Identity | The subject of experiences |

Plus operators: **will**, **motivation** and **transcendence** (copy, move, transform elements).

## A first look (planned API)

```python
import gaiabasic as gb

world = gb.World("Frog pond", seed=42)
world.ontology  = gb.Monism(base="matter")
world.sentience = gb.Emergentism(
    threshold=gb.Complexity(min_neurons=10_000),
    causal=False,              # experience has no effect on matter
)
world.identity  = gb.ClosedIndividualism()

world.populate(gb.species.Frog, n=200)
world.populate(gb.species.Fly,  n=5_000)

report = world.run(steps=50_000)
print(report.coherence)
print(report.valence_balance)
print(report.selection_pressure("sentience"))
```

The same world as a `.gaia` file:

```
WORLD "Frog pond" SEED 42
SUBSTANCE monism OF matter
SENTIENCE emergent WHEN neurons > 10000 CAUSAL no
IDENTITY closed
POPULATE frog 200
POPULATE fly 5000
RUN 50000 STEPS
REPORT coherence, valence_balance, selection("sentience")
```

## Planned package layout

```
gaiabasic/
  world.py        World, clock, space, seed
  elements.py     Matter, Idea, Experience, Identity
  operators.py    Will, Motivation, copy / move / transform
  substance.py    Monism, Dualism, Trialism, Quadrialism, Pluralism
  sentience.py    Emergentism, Immersionism, Panpsychism, ...
  identity.py     Closed / Empty / Open individualism
  agents.py       organisms, rules, memory, reproduction
  species/        ready-made organisms
  theory.py       Theory, the A–I theory map, presets, theory search
  evaluate.py     coherence, viability, valence accounting, comparison
  lang/           parser and runner for .gaia files
examples/
docs/
tests/
```

## Examples

See [gaiabasic.com/examples.html](https://gaiabasic.com/examples.html):

1. Emergentism versus immersionism
2. Useful or inevitable? Causal versus epiphenomenal sentience
3. P-zombies and motivation
4. Gradients of bliss
5. Is there more suffering than enjoyment in nature?
6. The evolution of pleasure
7. Identity and transcendence
8. Evolving theories of sentience with a genetic algorithm

## Roadmap

- [x] Concepts: taxonomies of substance, sentience and identity; maps of theories
- [ ] Core data model and world loop
- [ ] v0.1: monism, dualism, emergentism, epiphenomenalism, closed individualism, first examples
- [ ] Immersionism, panpsychism, identity models, transcendence operators
- [ ] `.gaia` language
- [ ] Theory search and the Sentience Research projects

## Background

- [Simulation of philosophical hypotheses about sentience](https://manuherran.com/simulacion-de-hipotesis-filosoficas-sobre-la-sintiencia-un-sistema-para-comprender-y-evaluar-teorias-metafisicas-de-la-sintiencia/)
- [What kinds of element make up reality?](https://manuherran.com/cuales-son-los-diferentes-tipos-de-elementos-que-constituyen-la-realidad-en-su-aspecto-mas-esencial/)
- [A map of the metaphysical theories of sentience](https://manuherran.com/un-mapa-de-las-teorias-metafisicas-de-la-sintiencia/)
- [A map of theories of consciousness, sentience and identity](https://manuherran.com/un-mapa-de-teorias-enfoques-y-paradigmas-relacionados-con-la-consciencia-la-sintiencia-y-la-identidad/)

## Contributing

Philosophers, scientists and programmers are all welcome. A clearly stated theory, with its assumptions listed, is as valuable as code. Please open an issue or a discussion.

## License

[MIT](LICENSE)

## Author

[Manu Herrán](https://manuherran.com/) · [Sentience Research](https://sentience-research.org/) · [Unbiased Machine](https://unbiasedmachine.com/)
