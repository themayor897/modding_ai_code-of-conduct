# Part 3 — Extending to Other Games

Part 1 is deliberately game-neutral, and so is the disclosure tag standard it defines. To adapt the Code to another game, add:

- a **game file** in `games/`, covering that game's versions and modding framework; and
- a **stack file** in `stacks/`, if one does not already exist for the language and engine the game is modded in. It holds the capability check for rule 5.6, so authors know what to search for.

The core rules stay the same.
