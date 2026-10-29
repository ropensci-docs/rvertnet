# Changelog

## rvertnet (development version)

## rvertnet 0.8.4

CRAN release: 2024-02-15

- remove hardcoded figure that caused failed vignette build on 2 CRAN
  check runners with old pandoc versions

## rvertnet 0.8.3

CRAN release: 2024-02-13

#### MINOR IMPROVEMENTS

- new maintainer
  ([\#71](https://github.com/ropensci/rvertnet/issues/71))
- fix CI
- refresh test fixtures
  ([\#71](https://github.com/ropensci/rvertnet/issues/71))
- remove plyr from examples
- refresh Darwin core terms and move to data object
- refresh vignette and its pre-compilation
- update Makefile
- update roxygen2 and documentation fixes
- remove outdated files

#### BUG FIXES

- fix class handling in vertmap to allow tibble input
- allow vignette to build
- fix ggplot2 deprecation warning
  ([\#71](https://github.com/ropensci/rvertnet/issues/71))

## rvertnet 0.8.2

CRAN release: 2021-05-13

#### MINOR IMPROVEMENTS

- vignette fix

## rvertnet 0.8.0

CRAN release: 2020-01-29

#### NEW FEATURES

- [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  and
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  reworked: both functions now have the first parameter as `...`, which
  accepts any valid query parameter. There were so many query parameters
  for these functions it was a bit overwhelming. See
  [`?searchbyterm`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  docs for details
  ([\#66](https://github.com/ropensci/rvertnet/issues/66))

#### MINOR IMPROVEMENTS

- decode the request URL before printing to the R console so users can
  more easily see what request they have done
  ([\#67](https://github.com/ropensci/rvertnet/issues/67))
- vignette title fix
  ([\#68](https://github.com/ropensci/rvertnet/issues/68))

#### BUG FIXES

- [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  fix: booleans need to be converted to VertNet’s expected `0/1` instead
  of `true/false`
  ([\#66](https://github.com/ropensci/rvertnet/issues/66))

## rvertnet 0.7.0

CRAN release: 2018-04-17

#### BUG FIXES

- add month and day params to `searchbyterm`
  ([\#64](https://github.com/ropensci/rvertnet/issues/64))

## rvertnet 0.6.2

CRAN release: 2017-10-11

#### BUG FIXES

- A small data source used in one function was on the web, and was
  moved - that data source now within the pkg as quite small, and now
  pkg won’t break when the file is moved again
  ([\#61](https://github.com/ropensci/rvertnet/issues/61))
  ([\#62](https://github.com/ropensci/rvertnet/issues/62))

## rvertnet 0.6.0

CRAN release: 2017-08-15

Added Code of Conduct.

#### NEW FEATURES

- Now using `crul` package for HTTP requests instead of `httr`
  ([\#57](https://github.com/ropensci/rvertnet/issues/57))
- Note that `verbose` parameter has been replaced with `messages`
  throughout the package.
- Now with function for search for trait data:
  [`traitsearch()`](https://docs.ropensci.org/rvertnet/reference/traitsearch.md)
  ([\#55](https://github.com/ropensci/rvertnet/issues/55))

#### DEFUNCT AND DEPRECATED

- All `dump` functions are now defunct. Those functions tried to help
  users work with bulk Vertnet data - the setup has gotten too complex
  ([\#56](https://github.com/ropensci/rvertnet/issues/56))

#### MINOR IMPROVEMENTS

- Improvements to documentation for
  [`traitsearch()`](https://docs.ropensci.org/rvertnet/reference/traitsearch.md)
  function on what fields have given data
  ([\#58](https://github.com/ropensci/rvertnet/issues/58)) thanks
  [@gaurav](https://github.com/gaurav)
- [`vertsearch()`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md)
  and
  [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  gain new parameter `only_dwc`, which allows to optionally only return
  Darwin Core fields

#### BUG FIXES

- Small fix to
  [`vertsummary()`](https://docs.ropensci.org/rvertnet/reference/vertsummary.md)
  ([\#59](https://github.com/ropensci/rvertnet/issues/59))

## rvertnet 0.5.0

CRAN release: 2016-09-23

#### NEW FEATURES

- [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  gains new parameter `query` to allow full text search, much like
  [`vertsearch()`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md),
  but with the ability to also use all the parameters available in
  [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  ([\#53](https://github.com/ropensci/rvertnet/issues/53))

#### MINOR IMPROVEMENTS

- Use
  [`dplyr::bind_rows`](https://dplyr.tidyverse.org/reference/bind_rows.html)
  instead of the deprecated `dplyr::rbind_all`
  ([\#51](https://github.com/ropensci/rvertnet/issues/51))
- remove personal email address from tests
  ([\#52](https://github.com/ropensci/rvertnet/issues/52))
- Namespace base R pkg fxn calls (`methods`/`stats`/`utils`), and
  removed some package dependencies that we didn’t really need (`plyr`)
  ([\#54](https://github.com/ropensci/rvertnet/issues/54))

## rvertnet 0.4.4

CRAN release: 2016-04-14

#### MINOR IMPROVEMENTS

- Updated docs to better indicate how to use the cursor feature
  ([\#49](https://github.com/ropensci/rvertnet/issues/49))
- Now using explicit encoding specification when using `httr::content()`
  ([\#47](https://github.com/ropensci/rvertnet/issues/47))

#### BUG FIXES

- Fixed `externalptr` error in the internal `vert_GET()` function
  ([\#48](https://github.com/ropensci/rvertnet/issues/48))

## rvertnet 0.4.1

CRAN release: 2015-12-02

#### BUG FIXES

- Fixed a bug in
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  in which we had forgotten to do internal conversion of logical input
  to 0/1 needed by the web API
  ([\#46](https://github.com/ropensci/rvertnet/issues/46))

## rvertnet 0.4.0

CRAN release: 2015-11-26

#### NEW FEATURES

- New set of functions to make working with VertNet data dumps easier.
  [`dump_links()`](https://docs.ropensci.org/rvertnet/reference/dump-defunct.md)
  gives you links to various data dump resources;
  [`dump_init()`](https://docs.ropensci.org/rvertnet/reference/dump-defunct.md)
  initialized a SQLite database connection;
  [`dump_tbl()`](https://docs.ropensci.org/rvertnet/reference/dump-defunct.md)
  creates a
  [`dplyr::tbl`](https://dplyr.tidyverse.org/reference/tbl.html) object,
  which can then be used in a `dplyr` query. This setup requires that
  the user manually download data dumps uncompress, and load into
  SQLite. We hope to make this process easier in the future.
  ([\#36](https://github.com/ropensci/rvertnet/issues/36))

#### MINOR IMPROVEMENTS

- Fixes to
  [`vertmap()`](https://docs.ropensci.org/rvertnet/reference/vertmap.md)
  for new `ggplot2` version
  ([\#43](https://github.com/ropensci/rvertnet/issues/43))
- Added note to docs for
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  for how to read in data after obtaining the data
  ([\#44](https://github.com/ropensci/rvertnet/issues/44))

#### BUG FIXES

- Fix to the
  [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  function. When the parameter `stateprovince` was used, lead to error,
  as that param requires different handling than other params.
  ([\#45](https://github.com/ropensci/rvertnet/issues/45))

## rvertnet 0.3.4

CRAN release: 2015-09-16

#### NEW FEATURES

- New function
  [`vert_id()`](https://docs.ropensci.org/rvertnet/reference/vert_id.md)
  to get occurrence records by occurenceid, that is, single occurrence
  ids. ([\#40](https://github.com/ropensci/rvertnet/issues/40))

#### MINOR IMPROVEMENTS

- Explicitly import non-base R functions
  ([\#39](https://github.com/ropensci/rvertnet/issues/39))

#### BUG FIXES

- Lowercase `occurenceID` to `occurrenceid` to simplify life
  ([\#41](https://github.com/ropensci/rvertnet/issues/41))

## rvertnet 0.3.0

CRAN release: 2015-06-26

#### NEW FEATURES

- [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md)
  and
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  have some parameters that accept multiple values. Fixed to allow this
  ([\#37](https://github.com/ropensci/rvertnet/issues/37))
- Internals of
  [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md),
  [`spatialsearch()`](https://docs.ropensci.org/rvertnet/reference/spatialsearch.md),
  and
  [`vertsearch()`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md)
  reworked to use cursor so we internally do paging for you for bigger
  result sets. ([\#25](https://github.com/ropensci/rvertnet/issues/25))

#### MINOR IMPROVEMENTS

- Replaced `data.table` import with `dplyr`
- Using `skip_on_cran()`
  ([\#38](https://github.com/ropensci/rvertnet/issues/38))
- Minor vignette updates
  ([\#35](https://github.com/ropensci/rvertnet/issues/35))
- Metadata now returned in data requests
  ([\#33](https://github.com/ropensci/rvertnet/issues/33))

## rvertnet 0.2.2

CRAN release: 2015-01-22

Package completely reworked for the new VertNet API.

#### NEW FEATURES

- The functions
  [`vertavailablemaps()`](https://docs.ropensci.org/rvertnet/reference/vertavailablemaps-defunct.md),
  [`vertlocations()`](https://docs.ropensci.org/rvertnet/reference/vertlocations-defunct.md),
  [`vertoccurrence()`](https://docs.ropensci.org/rvertnet/reference/vertoccurrence-defunct.md),
  [`vertoccurrencecount()`](https://docs.ropensci.org/rvertnet/reference/vertoccurrencecount-defunct.md),
  [`vertproviders()`](https://docs.ropensci.org/rvertnet/reference/vertproviders-defunct.md),
  [`verttaxa()`](https://docs.ropensci.org/rvertnet/reference/verttaxa-defunct.md)
  are now defunct. You can call these functions, but they print an error
  message, saying they are defunct.
- Gained new functions
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md),
  [`searchbyterm()`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md),
  [`spatialsearch()`](https://docs.ropensci.org/rvertnet/reference/spatialsearch.md),
  and
  [`vertsummary()`](https://docs.ropensci.org/rvertnet/reference/vertsummary.md).
- Gained new author: Chris Ray

#### MINOR IMPROVEMENTS

- `RJSONIO` replaced with `jsonlite`
- Changed from CC0 to MIT license

## rvertnet 0.0-5

CRAN release: 2012-11-23

#### NEW FEATURES

- released to CRAN
