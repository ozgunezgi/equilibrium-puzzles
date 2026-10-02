# Equilibrium Puzzles

A browser game about Nash equilibrium, and the notebooks that build everything underneath it.

**[Play the game →](https://ozgunezgi.github.io/equilibrium-puzzles/)**

A Nash equilibrium is an outcome in which no player can do better by changing only their own move. This repository approaches it from three sides: computing equilibria exactly, watching learning algorithms try to reach them by playing, and turning both into a game where people do the same.

## The game

`index.html` is the whole game: one file, no build step, no server. It has two parts.

**Puzzles.** Small games from the literature, from the Prisoner's Dilemma and Matching Pennies to penalty kicks and the Battle of the Sexes. Each level has three modes:

- *Solve:* select the cells nobody wants to leave, or set the mix of moves that makes the other player indifferent.
- *Watch learners:* hand the same game to two copies of fictitious play, regret matching or Q-learning and see where they end up.
- *Play the machine:* play the game yourself against one of those learners.

**Play.** The learning rules become characters.

- *Mystery opponents:* eight opponents play Rock-Paper-Scissors by hidden rules. Beat each one, then name its rule.
- *Tournament:* every character plays every other one, as in Axelrod's tournaments, in Rock-Paper-Scissors or the Prisoner's Dilemma.
- *Evolution:* strategies that earn more than the average spread through a population. In the repeated Prisoner's Dilemma this shows when cooperation survives; in Rock-Paper-Scissors the population circles the equilibrium; in Hawks and Doves it settles on a mix.

## The notebooks

| Notebook | What it covers |
|---|---|
| [`01_computing_equilibria`](notebooks/01_computing_equilibria.ipynb) | Best responses, dominance and iterated elimination, zero-sum games as linear programs, support enumeration, domination by mixed strategies. Results are checked against [`nashpy`](https://github.com/drvinceknight/Nashpy). |
| [`02_learning_in_games`](notebooks/02_learning_in_games.ipynb) | Fictitious play, regret matching and Q-learning, measured with NashConv. When the average strategy converges and the current one does not, and Shapley's game, where both fail. |
| [`03_levels_and_generator`](notebooks/03_levels_and_generator.ipynb) | The level format the game uses, an inverse linear program for the redesign puzzle, a generator for new puzzles, and a difficulty measure based on how long regret matching takes to solve each one. |

The main thread follows Shoham and Leyton-Brown, *Multiagent Systems* (2009). Each notebook cites the original papers for the methods it implements.

## Layout

```
index.html        the game
levels/           puzzle files written by notebook 03 (the game also carries a copy)
notebooks/        01, 02, 03
requirements.txt
```

## Running

Notebooks:

```
pip install -r requirements.txt
jupyter notebook notebooks/
```

The game: open `index.html` in a browser, or serve the folder with `python -m http.server` so it reads the files in `levels/`.

## License

MIT. The rock, paper and scissors drawings are my own.
