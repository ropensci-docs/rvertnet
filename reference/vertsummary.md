# Summarize a set of records downloaded from VertNet.

Creates a simple summary of data returned by a VertNet search.

## Usage

``` r
vertsummary(input, verbose = TRUE)
```

## Arguments

- input:

  Output from
  [`vertsearch`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md),
  [`searchbyterm`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md),
  or
  [`spatialsearch`](https://docs.ropensci.org/rvertnet/reference/spatialsearch.md).
  Required.

- verbose:

  Print progress and information messages. Default: TRUE

## Value

A list of summary statistics

## Details

`vertsummary` provides information on the sources, types and extent of
data returned by a VertNet search.

## Examples

``` r
if (FALSE) { # \dontrun{
# get occurrence records
recs <- vertsearch("Junco hyemalis", limit = 10)

# summarize occurrence records
vertsummary(recs)

vertsummary(vertsearch("Oncorhynchus clarki henshawi"))
} # }
```
