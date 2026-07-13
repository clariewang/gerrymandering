# Gerrymandering Analysis
 
*2024 Map vs. Proposed AB 604 Map*
 
This project looks at how a proposed California congressional redistricting map (AB 604) would have changed 2024 election outcomes. It uses public precinct level vote data and shapefiles.
 
AB 604's district lines did not exist in 2024, so votes had to be reallocated from the old precinct geography onto the new districts. I used two independent reallocation methods, area weighted interpolation and population weighted block allocation, to check whether the results held up regardless of method, rather than being an artifact of just one approach.
 
## Key findings
 
Democrats would hold 46 of 52 districts under the new map, using either reallocation method. Both the mean median score and the efficiency gap shift toward Democrats under the new map. Approach A and Approach B agree on every single district winner, even though they rest on completely different assumptions about how votes are distributed within a precinct. That agreement is itself evidence that the shift is real and not just a byproduct of one method's assumptions.
 
## Tools
 
R, sf, tidyverse, Quarto with Typst output
 
## Files
 
`gerrymandering-report.qmd` is the full analysis source, including data cleaning, spatial joins, metrics, and figures.
 
`gerrymandering-report.pdf` is the rendered report.
 
## Data
 
Data came from public California Statement of Vote precinct level files and shapefiles. It needed a fair amount of cleaning, including inconsistent precinct geographies, duplicate IDs, and placeholder values that looked like real numbers. The raw data files are not included in this repo due to their size, so the qmd is shared as a record of the full pipeline rather than something meant to be re-run as is.