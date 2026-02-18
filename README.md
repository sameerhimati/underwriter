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

## Stack
- Python 3.14, numpy
- Pydantic for model validation
- Typer + Rich for CLI

## Status
🟡 Not started
