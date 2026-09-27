# Equilibrium Puzzles

A browser puzzle game about Nash equilibrium, and the game theory underneath it.

This repository is being built in steps. It starts with solvers written from scratch, moves on to learning algorithms that try to reach equilibrium by playing, and ends in the game itself, where people find equilibria and play against those algorithms. Each step is a worked notebook that explains the theory, implements it, and checks the result.

## Status

- [x] **01 · Computing equilibria:** best responses, dominance, zero-sum games as linear programs, support enumeration
- [ ] **02 · Learning in games:** fictitious play, regret matching, Q-learning, and what it means for learning to "converge"
- [ ] **03 · Levels and a puzzle generator:** a level format, an inverse LP for design puzzles, generated puzzles and a difficulty measure
- [ ] **The game:** find equilibria, set mixed strategies with sliders, redesign payoffs, and play against learning agents, in the browser

## 01 · Computing equilibria

[`notebooks/01_computing_equilibria.ipynb`](notebooks/01_computing_equilibria.ipynb) covers two-player normal-form games: expected payoffs and best responses, checking a Nash equilibrium, pure equilibria and iterated elimination of dominated strategies, zero-sum games solved as linear programs, support enumeration for all equilibria of a nondegenerate game, and domination by mixed strategies.

Each section works through a familiar game (Prisoner's Dilemma, Matching Pennies, Battle of the Sexes, Rock-Paper-Scissors). Support enumeration is compared with [`nashpy`](https://github.com/drvinceknight/Nashpy) on random games. The main thread follows Shoham & Leyton-Brown, *Multiagent Systems* (2009), and the notebook cites the original papers for each method.

## Running

```
pip install -r requirements.txt
jupyter notebook notebooks/
```

## License

MIT
