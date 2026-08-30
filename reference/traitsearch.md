# Trait focused search

Trait focused search

## Usage

``` r
traitsearch(
  taxon = NULL,
  has_mass = FALSE,
  has_length = FALSE,
  has_sex = FALSE,
  has_lifestage = FALSE,
  length_type = NULL,
  length = NULL,
  mass = NULL,
  limit = 1000,
  compact = TRUE,
  messages = TRUE,
  callopts = list(),
  ...
)
```

## Arguments

- taxon:

  (character) Taxonomic identifier or other text to search for

- has_mass:

  (logical) limit to records that have mass data (stored in `massing`).
  Default: `FALSE`

- has_length:

  (logical) limit to records that have length data (stored in
  `lengthinmm`). Default: `FALSE`

- has_sex:

  (logical) limit to records that have sex data (stored in `sex`).
  Default: `FALSE`

- has_lifestage:

  (logical) limit to records that have lifestage data (stored in
  `lifestage`). Default: `FALSE`

- length_type:

  (character) length type, one of 'total length', 'standard length',
  'snout-vent length', 'head-body length', 'fork length', 'total length
  range', 'standard length range', 'snout-vent length range', 'head-body
  length range', 'fork length range'. (stored in `lengthtype`) Default:
  `NULL`

- length:

  (list) list of query terms for length, e.g., "\< 100"

- mass:

  (list) list of query terms for mass, e.g., "\< 100"

- limit:

  (numeric) Limit on the number of records returned. If \>1000 results,
  we use a cursor internally, but you should still get up to the results
  you asked for. See also
  [`bigsearch`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  to get larger result sets in a text file via email.

- compact:

  Return a compact data frame (boolean)

- messages:

  Print progress and information messages. Default: TRUE

- callopts:

  curl options in a list passed on to
  [`HttpClient`](https://docs.ropensci.org/crul/reference/HttpClient.html),
  see examples

- ...:

  (character) Additional search terms. These must be unnamed

## Value

a list, same as returned by
[`vertsearch`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md),
with data in the `data` slot

## Details

Wraps
[`vertsearch`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md),
with some of the same parameters, but with additional parameters added
to make querying for traits easy.

## Examples

``` r
if (FALSE) { # \dontrun{
traitsearch(has_mass = TRUE, limit = 3)
traitsearch(has_lifestage = TRUE)
traitsearch(has_mass = TRUE, has_length = TRUE)
res <- traitsearch(length_type = "total length",
  length = list(">= 300", "<= 1000"))
summary(as.numeric(res$data$lengthinmm))
res <- traitsearch(has_mass = TRUE, mass = list(">= 20", "<= 500"))
summary(as.numeric(res$data$massing))

traitsearch(taxon = "aves", has_mass = TRUE, limit = 100)
} # }
```
