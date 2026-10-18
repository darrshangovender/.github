# Contributing

Thanks for taking the time to improve one of these projects. They are small, focused libraries, and the bar for changes is the same bar they were built to: tested, reproducible, honest.

## Before you start

- **Bugs:** open an issue with the smallest input that reproduces it, what you expected, and what happened. A failing test is the best bug report.
- **Features:** open an issue first so we can agree on scope before you write code. Small, composable additions are far more likely to be merged than broad ones.
- **Security issues:** do not open a public issue — see [SECURITY.md](SECURITY.md).

## Development setup

Every repository follows the same layout:

```bash
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e ".[dev]"
make test        # or: pytest tests/
make lint        # or: ruff check .
```

Tests and examples run offline, with no API keys. Please keep it that way: if your change calls a model or an external service, put it behind an interface with a deterministic fake for tests.

## Pull request checklist

- [ ] `pytest tests/` passes and `ruff check .` is clean.
- [ ] New behaviour has tests; bug fixes include a regression test that fails without the fix.
- [ ] No test was weakened or deleted to make the suite pass.
- [ ] Any number added to a README is produced by a script in the repository, and the README says what it was measured on.
- [ ] `CHANGELOG.md` has an entry under `Unreleased`.

## Style

- Python 3.11+, type hints on public functions, Pydantic models at external boundaries.
- Line length 100, enforced by ruff.
- Prefer clear names and small functions over comments; comment the *why*, not the *what*.

By contributing you agree that your contribution is licensed under the repository's MIT licence.
