# Mystic Full English Coding Guide

Mystic is an English-first language.
Write what you mean in plain words.

Example style:

```my
make graphics = good, bad, terrible
when graphics_choice is good
    show "Great quality"
```

No curly braces. No semicolons. Indentation controls blocks.

## 1. Start Here

Run a file:

```powershell
.\mystic.bat run your_file.my
```

Project helpers:

```powershell
.\myst.bat init
.\myst.bat add nebula-ui
.\myst.bat remove nebula-ui
```

## 2. English Command Cheat Sheet

- `make name = value` -> create or update a value
- `make action main` -> create a function
- `make action greet with user` -> function with parameters
- `make blueprint Player` -> create a class
- `run main` -> call a function
- `run greet with "Aeo"` -> call with arguments
- `show "hello"` -> print
- `ask "Your name?" and save as name` -> input into variable
- `when / or when / otherwise` -> if / elif / else
- `repeat each item in list` -> for loop
- `keep doing condition` -> while loop
- `keep doing forever` -> endless loop
- `add value into list_name` -> append
- `remove value from list_name` -> remove
- `stop loop` -> break
- `skip to next` -> continue
- `stop action` -> return
- `stop action with value` -> return value
- `try this / if error / always` -> try / catch / finally

## 3. First Program

```my
make action main
    show "Hello from Mystic"

run main
```

## 4. Values and Variables

```my
make username = mystic_user
make level = 12
make premium = true
make rating = 4.8
make graphics_modes = good, bad, terrible

show username
show level
show graphics_modes
```

Rules:
- Bare words in `make` become text automatically.
- Comma-separated words become a text list automatically.
- Numbers and booleans stay numeric/boolean.

## 5. Asking the User for Input

```my
make action main
    ask "What is your name? " and save as user
    ask "Pick graphics (good/bad/terrible): " and save as picked

    show "Welcome " + user
    show "You picked: " + picked

run main
```

## 6. Decisions (When / Otherwise)

```my
make action main
    ask "Graphics mode: " and save as picked

    when picked is good
        show "Smooth visuals enabled"
    or when picked is bad
        show "Performance mode enabled"
    otherwise
        show "Fallback mode enabled"

run main
```

Also supported:

```my
when picked is not good
    show "Not high quality"
```

## 7. Loops

Repeat through a list:

```my
make modes = easy, medium, hard, god_like
repeat each mode in modes
    show mode
```

While loop:

```my
make number = 1
keep doing number <= 3
    show number
    make number = number + 1
```

Forever loop with manual stop:

```my
make action main
    make count = 0
    keep doing forever
        make count = count + 1
        show count
        when count >= 3
            stop loop

run main
```

## 8. List Control in English

```my
make players = kai, nova
add "aria" into players
remove "kai" from players

repeat each p in players
    show p
```

## 9. Actions (Functions)

Simple action:

```my
make action greet with user
    show "Hello " + user
```

Return values:

```my
make action add with a, b
    stop action with a + b
```

Use actions:

```my
make action main
    run greet with "Aeo"
    make total = add(5, 7)
    show "Total: " + str(total)

run main
```

## 10. Blueprints (Classes)

```my
make blueprint Player
    property name = "guest"
    property score = 0

    make action add_points with amount
        self.score = self.score + amount

make action main
    make user = Player()
    user.name = "MysticHero"
    user.add_points(100)
    show user.name + " score: " + str(user.score)

run main
```

## 11. Error Handling

```my
try this
    make content = read_file("profile.txt")
    show content
if error as err
    show "Error: " + err.message
always
    show "Finished"
```

## 12. Graphics Example (Your Style)

```my
make action main
    make user = player_one
    make graphics = good, bad, terrible

    show "Hello " + user
    show "Pick graphics quality:"
    repeat each option in graphics
        show "- " + option

    ask "Type one option: " and save as picked

    when picked is good
        show "Graphics set to GOOD"
    or when picked is bad
        show "Graphics set to BAD"
    otherwise
        show "Graphics set to TERRIBLE"

run main
```

## 13. Mini Project: Text Settings App

```my
make action show_menu
    show "1. set graphics"
    show "2. set player name"
    show "3. view settings"
    show "4. exit"

make action main
    make player_name = guest
    make graphics = good

    keep doing forever
        run show_menu
        ask "Choose (1-4): " and save as choice

        when choice is 1
            ask "Graphics (good/bad/terrible): " and save as graphics
        or when choice is 2
            ask "Player name: " and save as player_name
        or when choice is 3
            show "Player: " + player_name
            show "Graphics: " + graphics
        otherwise
            show "Goodbye"
            stop loop

run main
```

## 14. Learning Path (Easy -> Medium -> Hard -> God-Like)

Easy goals:
- `make`
- `show`
- simple loops

Medium goals:
- `make action`
- `run`
- conditions with `when`

Hard goals:
- `make blueprint`
- list operations (`add into`, `remove from`)
- error handling

God-Like goals:
- multi-file structure
- settings + gameplay + UI modules
- events and async design patterns

## 15. Common Mistakes and Fixes

- Mistake: no indentation inside actions/conditions.
  Fix: indent nested lines with 4 spaces.
- Mistake: `run main()` instead of `run main`.
  Fix: use English call style `run main`.
- Mistake: forget quotes when needed in normal expressions.
  Fix: use `"text"` when not using `make` auto-word behavior.
- Mistake: mix tabs and spaces.
  Fix: use spaces only.

## 16. Suggested File Layout

```text
my-game/
  mystic.toml
  main.my
  settings.my
  player.my
  world.my
  ui/
    menu.my
```

## 17. Daily Practice Plan

Day 1:
- Hello program
- variables
- `show`

Day 2:
- conditions
- loops
- list operations

Day 3:
- actions and return values
- mini calculator

Day 4:
- blueprints and object state
- score/inventory system

Day 5:
- build text settings app
- split into multiple files

Mystic is now tuned for English-style coding.

## 18. Share Mystic on GitHub

To let other users use Mystic:

1. Push this project to GitHub.
2. Tell users to install from your repo:

```powershell
python -m pip install "git+https://github.com/<your-user>/<your-repo>.git"
```

3. Users can then run:

```powershell
mystic run hello.my
```

See full publish steps:
- `docs/GITHUB_PUBLISH.md`
