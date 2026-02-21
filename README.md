# Mystic Language

Mystic is a beginner-friendly, modern programming language with full English-style syntax and powerful app architecture.

- File extension: `.my`
- Language CLI: `mystic run main.my`
- Package manager CLI: `myst add <package>`

## Quick Start

1. Run a script:
   - `.\mystic.bat run samples\main.my`
2. Try package manager:
   - `.\myst.bat init`
   - `.\myst.bat add nebula-ui`
3. Read docs:
   - `docs/MYSTIC_SPEC.md`
   - `docs/GRAMMAR.ebnf`
   - `learningCode.md`
   - `docs/GITHUB_PUBLISH.md`
   - `docs/MYSTIC_STUDIO_ROADMAP.md`

## Install From GitHub (For Other Users)

Once this repo is on GitHub, users can install Mystic directly:

```powershell
python -m pip install "git+https://github.com/<your-user>/<your-repo>.git"
```

Then they can run:

```powershell
mystic run main.my
myst init
```

If `mystic` is not recognized on Windows, add your Python Scripts folder to PATH.

## Learn Mystic: Easy -> Medium -> Hard -> God-Like

Use this path to teach users progressively.

### 1. Easy
Goal: learn variables, loops, and `show`.

```my
make action main
    make name = Mystic
    make levels = Easy, Medium, Hard, God-Like

    show "Hello " + name
    repeat each level in levels
        show "- " + level

run main
```

Run:
- `.\mystic.bat run your_file.my`

### 2. Medium
Goal: learn classes, properties, and methods.

```my
make blueprint Player
    property name = "Guest"
    property score = 0

    make action add_points with points
        self.score = self.score + points

make action main
    make p = Player()
    p.name = "Aeo"
    p.add_points(25)
    show p.name + " score: " + str(p.score)

run main
```

### 3. Hard
Goal: combine logic + UI-style options flow (dropdown-like choices).

```my
make action main
    make graphics_options = simple, plain, hard, smooth, fun
    show "Pick graphics mode:"

    repeat each mode in graphics_options
        show "- " + mode

    make selected_mode = input("Type mode: ")
    when selected_mode is smooth
        show "Smooth graphics enabled."
    or when selected_mode is fun
        show "Fun graphics enabled."
    otherwise
        show "Mode set to: " + selected_mode

run main
```

### 4. God-Like
Goal: architect bigger systems with modules, error handling, async thinking, and clean structure.

Read the full guide:
- `learningCode.md`

Tips:
- Start with `Easy`, then copy and upgrade it.
- Use English-style Mystic keywords: `make`, `make action`, `make blueprint`, `show`, `when`, `otherwise`, `run`.
- Check `samples/main.my` and `samples/Trigger.my` for ready examples.

## Repository Contents

- Language documentation and roadmap
- Draft EBNF grammar
- Prototype Mystic-to-Python transpiler runtime
- CLI (`mystic`) and package manager (`myst`) starter implementation
- GitHub publish guide
- Mystic Studio roadmap (future dedicated IDE)

This is a functional starter implementation, not a full production compiler/VM yet.
