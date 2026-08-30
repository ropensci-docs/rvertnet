# Make a simple map to visualize VertNet data.

Plots record locations on a world or regional map using
latitude/longitude data returned by a VertNet search.

## Usage

``` r
vertmap(
  input = NULL,
  mapdatabase = "world",
  region = ".",
  geom = geom_point,
  jitter = NULL
)
```

## Arguments

- input:

  Output from
  [`vertsearch`](https://docs.ropensci.org/rvertnet/reference/vertsearch.md),
  [`searchbyterm`](https://docs.ropensci.org/rvertnet/reference/searchbyterm.md),
  or
  [`spatialsearch`](https://docs.ropensci.org/rvertnet/reference/spatialsearch.md).
  Must include columns "decimallatitude" and "decimallongitude"

- mapdatabase:

  The base map on which your data are displayed; what you choose here
  determines what you can choose in the region parameter; one of:
  county, state, usa, world, world2, france, italy, or nz

- region:

  The region in which your data are displayed; to see region names for
  the "world" database layer, run
  `sort(unique(map_data("world")$region))` after loading packages maps
  and ggplot2; to see region names for the US "state" layer, run
  `sort(unique(map_data("state")$region))`

- geom:

  Specifies the type of object being plotted; one of: `geom_point` or
  `geom_jitter` (do not use quotes)

- jitter:

  If `geom = geom_jitter`, the amount by which to jitter points in
  width, height, or both. Default

## Value

Map of record locations displayed on the selected base map

## Details

`vertmap` uses decimal latitude and longitude data in records generated
by an rvertnet search to display returned records on a specified base
map. Taxa are color-coded by scientific name, if available. Adapt the
vertmap code to construct maps according to your own specifications.

## Examples

``` r
if (FALSE) { # \dontrun{
out <- vertsearch("Junco hyemalis") # get occurrence records
vertmap(out)                        # map occurrence records

# Records are color coded by dwc term "scientificname" - sometimes unavailble
out <- vertsearch("mustela nigripes")
vertmap(input = out, mapdatabase = "state")

# Use searchbyterm() to match records with mapped region
spec <- searchbyterm(genus = "ochotona", specificepithet = "princeps", state = "california",
limit = 200)
vertmap(input = spec, mapdatabase = "state", region = "california")

# Many species
splist <- c("Accipiter erythronemius", "Aix sponsa", "Haliaeetus leucocephalus",
    "Corvus corone", "Threskiornis molucca", "Merops malimbicus")
out <- lapply(splist, function(x) vertsearch(t=x, lim=100))
out <- dplyr::bind_rows(lapply(out, "[[", "data"))
vertmap(out)
## jitter points
library("ggplot2")
vertmap(out, geom = geom_jitter, jitter = position_jitter(1, 6))
} # }
```
