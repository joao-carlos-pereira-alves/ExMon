# ExMon

**This is a simple command line application that simulates a battle game agains the computer, as part of Udemy's ELixir and Phoenix do zero online course. The application consists in the creation of a player and a selection of two fight moves and a healing one. Once the game is started, the player makes a move, and then the computer will automatically do one, until one of them has no life points remaining.**

# Rules:

**Both players will start with 100 life points. Both player has the same available moves:

* An average attack that will deal between 18 and 25 points of damage to the opponent.
* A random attack that will deal between 10 and 35 points of damage to the opponent.
* A heal move that will recover between 18 and 25 life points to the player.

The player always start the match. After creating a player (see how to play below) and making a move, the computer will automatically do a move as well, until one of them has zero life points, and we'll have a winner :)**

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `ex_mon` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:ex_mon, "~> 0.1.0"}
  ]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at <https://hexdocs.pm/ex_mon>.

