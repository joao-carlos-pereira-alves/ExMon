# ExMon

**This is a simple command line application that simulates a battle game agains the computer, as part of Udemy's ELixir and Phoenix do zero online course. The application consists in the creation of a player and a selection of two fight moves and a healing one. Once the game is started, the player makes a move, and then the computer will automatically do one, until one of them has no life points remaining.**

# Rules:

Both players will start with 100 life points. Both player has the same available moves:

* An average attack that will deal between 18 and 25 points of damage to the opponent.
* A random attack that will deal between 10 and 35 points of damage to the opponent.
* A heal move that will recover between 18 and 25 life points to the player.

The player always start the match. After creating a player (see how to play below) and making a move, the computer will automatically do a move as well, until one of them has zero life points, and we'll have a winner :)

## Installation

Clone this repo and execute the following commands insite the project directory.

1. Install the dependecies

```elixir
mix deps.get
```

2. Start Elixir's REPL

```elixir
iex -S mix
```

## How to play

1. Once started Elixir's REPL, create a player using the create_player/4 function. The parameters order are: name, average_move, random_move, healing_move. Keep in mind the names that you'll use, you will type them to make the moves. See the game rules above to see how each move works.

```elixir
iex> player = ExMon.create_player("maryplank", :kick, :punch, :heal)
```

You'll see your player as a response

```elixir
iex> player = ExMon.create_player("maryplank", :kick, :punch, :heal)
%ExMon.Player{
  life: 100,
  moves: %{move_avg: :punch, move_heal: :heal, move_rdn: :kick},
  name: "maryplank"
}
```

2. Start the game passing your player variable as a parameter.`

```iex> ExMon.start_game(player)```

And let the games begin

```elixir
====== The game has started! ======

%{
  computer: %ExMon.Player{
    life: 100,
    moves: %{move_avg: :kick, move_heal: :heal, move_rdn: :punch},
    name: "Robotinik"
  },
  player: %ExMon.Player{
    life: 100,
    moves: %{move_avg: :punch, move_heal: :heal, move_rdn: :kick},
    name: "maryplank"
  },
  status: :started,
  turn: :player
}
----------------------------------
:ok
```

3. Do one of the moves you named when creating the player and win this battle!

```elixir
iex> ExMon.make_move(:kick)
```

The computer will do his move and then will be your turn again and so on...

```elixir
====== Player attacked the computer dealing 28 points of damage ======


====== computer's turn ======

%{
  computer: %ExMon.Player{
    life: 72,
    moves: %{move_avg: :kick, move_heal: :heal, move_rdn: :punch},
    name: "Robotinik"
  },
  player: %ExMon.Player{
    life: 100,
    moves: %{move_avg: :punch, move_heal: :heal, move_rdn: :kick},
    name: "maryplank"
  },
  status: :continue,
  turn: :computer
}
----------------------------------

====== Computer attacked the player dealing 23 points of damage ======


====== player's turn ======

%{
  computer: %ExMon.Player{
    life: 72,
    moves: %{move_avg: :kick, move_heal: :heal, move_rdn: :punch},
    name: "Robotinik"
  },
  player: %ExMon.Player{
    life: 77,
    moves: %{move_avg: :punch, move_heal: :heal, move_rdn: :kick},
    name: "maryplank"
  },
  status: :continue,
  turn: :player
}
----------------------------------
:ok
```