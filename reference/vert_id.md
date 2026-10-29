# Search by Vertnet occurrence ID

Search by Vertnet occurrence ID

## Usage

``` r
vert_id(ids, compact = TRUE, messages = TRUE, ...)
```

## Arguments

- ids:

  (character) VertNet IDs, one or more. Required.

- compact:

  (logical) Return a compact data frame. That is, remove empty columns.
  Default: `TRUE`

- messages:

  (logical) Print progress and information messages. Default: `TRUE`

- ...:

  Curl arguments passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

A list, with data frame of search results, and list of metadata

## Details

VertNet IDs can be a variety of things, some URIs (i.e., with
http://...), while others start with `urn`.

Internally in this function we filter data to darwin core terms only. To
see what terms we use, see: `print(simple_dwc_terms)`.

See documentation for more information:
[`?simple_dwc_terms`](https://docs.ropensci.org/rvertnet/reference/simple_dwc_terms.md)

## Examples

``` r
if (FALSE) { # \dontrun{
vert_id(ids = "urn:catalog:CM:Herps:116520")
ids <- c("http://arctos.database.museum/guid/MSB:Mamm:56979?seid=1643089", 
         "urn:catalog:CM:Herps:116520",
         "urn:catalog:AUM:Fish:13271")
res <- vert_id(ids)
res$data$occurrenceid

out <- vertsearch(taxon = "aves", state = "california", limit = 5)
(ids <- out$data$occurrenceid)
res <- vert_id(ids)
identical(sort(res$data$occurrenceid), sort(ids))
} # }
```
