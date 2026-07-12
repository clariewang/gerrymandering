# Gerrymandering Analysis: 2024 Map vs. Proposed AB 604 Map

This project reconstructs how a proposed California congressional
redistricting map (AB 604) would have changed 2024 election outcomes,
using public precinct-level vote data and shapefiles.

Since AB 604's district lines didn't exist in 2024, votes had to be
reallocated from the old precinct geography onto the new districts.
I implemented two independent reallocation methods — area-weighted
interpolation and population-weighted block allocation — to check
whether the results were robust to that choice, rather than an
artifact of one method.

## Key findings

- Democrats would hold 46 of 52 districts under the new map, by either
  reallocation method.
- Both the mean-median score and efficiency gap shift toward a
  pro-Democratic direction under the new map.
- Approach A and Approach B agree on every district's winner, despite
  using entirely different assumptions about how votes are distributed
  within a precinct — which is itself evidence the direction of the
  shift is not an artifact of either method.

## Tools

R, sf, tidyverse, Quarto (Typst output)

## Files

- `gerrymandering-report.qmd` — full analysis source (data cleaning,
  spatial joins, metrics, figures)
- `gerrymandering-report.pdf` — rendered report

To reproduce, run:

```bash
quarto render gerrymandering-report.qmd
```

## Data

Data was sourced from public California Statement of Vote precinct-level
files and shapefiles, and required cleaning for inconsistent precinct
geographies, duplicate IDs, and placeholder values.
