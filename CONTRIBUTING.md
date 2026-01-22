# Contributing

Thanks for contributing to **telemetry-analytics-fastapi**!

This service provides aggregation/analytics endpoints for telemetry data. The goals are clean structure, testability, and predictable behavior.

## Changelog and decisions (required)
- **Update `CHANGELOG.md` on every push** (at minimum the `Unreleased` section).
- For major decisions (data model, storage choice, background jobs, API contract), **add/update an ADR** in `docs/decisions/`.

## Prerequisites
- Python 3.11+ (3.12 recommended)
- venv (or equivalent)

## Setup (venv)
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
```

## Run locally
```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

## Testing
```bash
pytest -q
```

## Linting
```bash
ruff check .
```

## Project conventions

### Suggested structure
- `app/api` — routes + dependencies
- `app/core` — settings/config + logging
- `app/services` — aggregation logic
- `app/repositories` — storage abstraction
- `app/models` — Pydantic models/domain types
- `tests/` — pytest tests

### Configuration
- Prefer typed settings driven by env variables.
- Keep local defaults sensible for development.

### Logging
- Use the `logging` module (no prints).
- Keep log messages consistent and actionable.

## Documentation
- Update `README.md` for endpoint/env changes.
- Update `docs/architecture.md` for flow/boundary changes.
- Add ADRs under `docs/decisions/` for major choices.

## Commit message guidelines
Use clear, imperative messages:
- "Add /health endpoint"
- "Implement basic aggregation query"
- "Add tests for aggregation service"

## Pull requests
- Include a summary and how to verify locally.
- Add tests for new behavior.
- Keep PRs small and focused.
