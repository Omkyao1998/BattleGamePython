# Turn-Based Battle Game (Python OOP)

A text-based, turn-based RPG battle in the terminal: a party of three heroes fights three enemies using attacks, magic and items. I built it to practise object-oriented design in Python.

## How it plays

Each turn, every hero picks one action:

1. **Attack** – deal random damage to a chosen enemy
2. **Magic** – cast a spell that costs MP (black magic damages, white magic heals)
3. **Items** – use potions, an elixir or a grenade from a shared inventory

Enemies then pick a target and either attack or cast a spell. The game ends when all enemies or all heroes are defeated. HP and MP are shown as coloured bars in the terminal.

## Design

| Class | File | Responsibility |
|---|---|---|
| `Person` | `Classes/game.py` | A hero or enemy: HP, MP, attack, defence, spells, items; takes damage, heals, chooses actions and targets, prints stat bars |
| `Spell` | `Classes/magic.py` | Name, MP cost, damage and type (black/white); generates random damage |
| `Item` | `Classes/inventory.py` | Name, type (potion, elixir, attack) and effect value |
| `bcolors` | `Classes/game.py` | ANSI colour codes for terminal output |

`main.py` creates the spells, items and characters, then runs the game loop.

OOP concepts used: classes and objects, encapsulation (each character manages its own HP/MP through methods), composition (a `Person` holds `Spell` and `Item` objects), and separating game data from game logic.

## How to run

No external packages needed (Python 3.8+).

```bash
git clone https://github.com/Omkyao1998/BattleGamePython.git
cd BattleGamePython
python main.py
```

Use a terminal that supports ANSI colours (most do; on Windows use Windows Terminal or PowerShell).

## What I would improve next

- Add a `Hero` / `Enemy` subclass split with different behaviour (inheritance)
- Validate user input so a wrong key doesn't crash the game
- Add unit tests for damage and healing

## Author

**Omkar Gokhale** · [GitHub](https://github.com/Omkyao1998)
