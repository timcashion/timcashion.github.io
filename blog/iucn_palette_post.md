<!-- README.md is generated from README.Rmd. Please edit that file -->
IUCN Palette
============

Make your plots with the official colours used by the IUCN according to
their style guide.

I wanted to give a bit more on the package I made for using IUCN palette
colours in in R. I built this as I wanted to do just that, align the
data I was representing with the official colours of the IUCN. The
framework for the package was the Wes Anderson
(package)\[<a href="https://github.com/karthik/wesanderson" class="uri">https://github.com/karthik/wesanderson</a>\]
which made this fairly simple for me. I built some additional features
to it though as people would be more likely to need only select colours.

The additional features are passed as arguments to the main function
‘iucn\_palette’ where you can exclude certain colours (exclude the
colour for ‘Extinct’ for example), or where you can select to just use
one (select only ‘Endangered’). Practically, if you’re only using one
this isn’t that different from putting the hexcode yourself, but the
package does allow you to easily switch between them and access these
colours when you need.

Installation
------------

``` r
#devtools::install_github("timcashion/IUCNpalette") 
```

Usage
-----

``` r
library("IUCNpalette")
# See all palettes
names(iucn_palettes)
#> [1] "CO"  "CR"  "EN"  "VU"  "NT"  "LC"  "DD"  "NE"  "All"
```

### All

``` r
iucn_palette(category="All")
```

![](figure/full-categories-1.png)

### Remove some categories

If you want to have most but remove some that aren’t in your plot:

``` r
iucn_palette(category="All", exclude=c("DD", "NE", "CO"))
```

![](figure/some-categories-1.png)

### Single category

If you want to only call a single category colour:

``` r
iucn_palette(category="EN")
```

![](figure/single-category-1.png)

![](IUCN_RGB.PNG)  
Source: Bland et al., 2016.

NOTE: This package is made for aligning graphics with the IUCN official
category colours, but is not endorsed in any way by the IUCN.

References
----------

-   Bland, L.M., Keith, D.A., Miller, R.M., Murray, N.J. and Rodríguez,
    J.P. (eds.) (2016). Guidelines for the application of IUCN Red List
    of Ecosystems Categories and Criteria, Version 1.0. Gland,
    Switzerland: IUCN. ix + 94pp.
    <a href="https://portals.iucn.org/library/sites/library/files/documents/2016-010.pdf" class="uri">https://portals.iucn.org/library/sites/library/files/documents/2016-010.pdf</a>
