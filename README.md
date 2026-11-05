# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a shipping quote
in dollars.  Zones are `local` and `regional`; weights must be positive.
`service` may be `"standard"` (default) or `"express"` — express adds $7.00 to
the standard rate.  An unknown service raises `ValueError`.

The command-line entry point prints a quote for an order:

```
python -m warehouse.cli 2 local
# $8.00

python -m warehouse.cli 2 local --service express
# $15.00
```
