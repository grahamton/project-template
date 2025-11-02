# Template Guide

Purpose
- A base educational template showing folder structure, docs, tests, and release practices. Includes your custom agent instructions in `AGENTS.md`.

What’s Included
- `src/` package with CLI entry (Typer), `tests/`, and docs (`README.md`, `RELEASE.md`, `CHANGELOG.md`, `ROADMAP.md`, `AGENTS.md`). Optional `webapp/`.

How To Use As A Template
1) Make this repo a GitHub Template: Settings -> General -> Template repository.
2) Create a new repo from the template.
3) Update metadata:
   - `pyproject.toml`: `[project].name`, `version`, `description`, and `[project.scripts]` CLI name.
   - `README.md`: title and overview.
   - Optional: remove `webapp/` if not needed.
4) Keep `AGENTS.md` to enforce contributor behavior.
5) Validate locally:
   - `python -m pip install -e .[dev]`
   - `ruff check .` and `black --check .`
   - `pytest -q`
   - If CLI kept: run `<cli-name> --help`

Educational Notes
- Use `RELEASE.md` for versioning and changelog hygiene.
- Keep core logic pure (no network/fs); let the CLI handle IO.
- Tests live in `tests/` and should include CLI smoke plus core routines.

