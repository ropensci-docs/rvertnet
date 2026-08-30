# Search VertNet archives using R

There are a variety of ways to search VertNet

## Search by term

Search for *Aves* in the state of *California*, limit to 10 records,
e.g.:

`searchbyterm(class = "Aves", state = "California", lim = 10, verbose = FALSE)`

Search for *Mustela nigripes* in the states of *Wyoming* or *South
Dakota*, limit to 20 records, e.g.:

`searchbyterm(genus = "Mustela", specificepithet = "nigripes", state = "(wyoming OR south dakota)", limit = 20, verbose=FALSE)`

## Big data

Specifies a termwise search (like
[`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)),
but requests that all available records be made available for download
as a tab-delimited text file.

`bigsearch(genus = "ochotona", rf = "pikaRecords", email = "big@search.luv")`

## Spatial search

`spatialsearch(lat = 33.529, lon = -105.694, radius = 2000, limit = 10, verbose = FALSE)`

## Full text search

Find records using a global full-text search of VertNet archives.

`vertsearch(taxon = "aves", state = "california")`

## No results?

It's possible to get no results when requesting data from VertNet, then
run the same function again 10 seconds later, and you do get a result.
I'm not sure why this is, something having to do with Vertnet's
infrastucture that I'm not aware of. Point is, if you are sure you
haven't made any mistakes with the parameters, etc., then simply run the
function call again.

## See also

Useful links:

- <https://github.com/ropensci/rvertnet>

- <https://docs.ropensci.org/rvertnet/>

- Report bugs at <https://github.com/ropensci/rvertnet/issues>

## Author

**Maintainer**: Dave Slager <slager@uw.edu>
([ORCID](https://orcid.org/0000-0003-2525-2039)) \[contributor\]

Authors:

- Scott Chamberlain <myrmecocystus@gmail.com>
  ([ORCID](https://orcid.org/0000-0003-1444-9135))

Other contributors:

- Chris Ray \[contributor\]

- Vijay Barve \[contributor\]
