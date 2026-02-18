# underwriter

## What This Is
Financial modeling engine for CRE acquisitions. Produces pro forma analysis with sensitivity tables.

## Key Constraints
- Assumptions must be explicit and configurable — no hidden defaults
- Every output number must be traceable to inputs
- Support multiple deal types: value-add industrial, NNN, sale-leaseback
- Output: JSON pro forma + Rich terminal tables + optional PDF

## Architecture
- Assumption templates: YAML files per deal type with default values
- Financial models: pure functions (inputs → outputs), no side effects
- Sensitivity engine: varies 1-2 inputs across ranges, produces matrix
- CLI: single property or batch comparison

## Tech
- Python 3.14, numpy, Pydantic, Typer + Rich
- No database — reads property JSON/CSV, writes results
- Use venv/bin/python and venv/bin/pytest

## Testing
- Known-answer tests: manually verified Excel outputs as fixtures
- Edge cases: zero vacancy, 100% vacancy, negative leverage
