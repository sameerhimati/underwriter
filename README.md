# underwriter

Runs pro forma financial models on commercial real estate properties. Takes property data + assumptions, outputs underwriting with sensitivity analysis.

## What it replaces
Associates manually building Excel models for each deal.

## Usage
```bash
underwriter run --property property.json --assumptions assumptions.yaml
underwriter sensitivity --property property.json --vary cap_rate,vacancy
underwriter compare --properties p1.json p2.json p3.json
```

## Models
- Stabilized yield analysis
- Cash-on-cash return
- IRR projection (5/7/10 year holds)
- Debt service coverage ratio
- Sensitivity tables (cap rate × vacancy, rent × exit cap)

## Input / Output

**Input:**
- Property JSON: `{ "address", "sqft", "price_per_sf", "rent_per_sf", "vacancy_pct", "opex_per_sf", "cap_rate" }`
- Assumptions YAML: financing terms, hold period, rent growth, exit cap
- Optional: `--vary` flag for sensitivity analysis (e.g. `--vary cap_rate,vacancy`)

**Output:**
- Pro forma JSON: `{ "noi", "value", "cash_on_cash", "irr_5yr", "irr_7yr", "irr_10yr", "dscr", "equity_multiple" }`
- Sensitivity mode: matrix JSON with varied inputs → outputs
- Rich terminal table for human review
- Exit code 0 on success, 1 on failure

## Stack
- Python 3.14, numpy
- Pydantic for model validation
- Typer + Rich for CLI

## Status
🟡 Not started
