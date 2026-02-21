# Contributing to Mystic

Thanks for contributing to Mystic.

## Setup

1. Use Python 3.10+.
2. From repository root:
   - `python -m pip install -e .`
3. Run samples:
   - `mystic run samples/main.my`
   - `mystic run samples/Trigger.my`

## Development Rules

- Keep Mystic syntax English-first.
- Preserve indentation-based structure.
- Add or update docs when adding syntax.
- Keep examples in `samples/` runnable.

## Quick Checks

- `python -m py_compile src/mystic/*.py src/myst/*.py mystic.py myst.py`

## Pull Request Checklist

- Syntax changes documented in `learningCode.md`
- README updated if user workflow changed
- Sample file added/updated if feature is user-facing
- Local compile checks pass
