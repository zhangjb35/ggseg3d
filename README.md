
# ggseg3d <img src='man/figures/logo.png' align="right" height="138.5" />

<!-- badges: start -->

[![Coverage
status](https://codecov.io/gh/LCBC-UiO/ggseg3d/branch/master/graph/badge.svg)](https://codecov.io/gh/LCBC-UiO/ggseg3d)
[![CRAN
status](https://www.r-pkg.org/badges/version/ggseg3d)](https://CRAN.R-project.org/package=ggseg3d)
[![Lifecycle:
maturing](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://lifecycle.r-lib.org/articles/stages.html)
[![R build
status](https://github.com/LCBC-UiO/ggseg3d/workflows/R-CMD-check/badge.svg)](https://github.com/LCBC-UiO/ggseg3d/actions)
<!-- badges: end -->

This package mainly contains a plotting function `ggseg3d` and
data.frames of different brain atlases for plotting. Plotting results of
analyses on regions or networks often involves swapping between
statistical tools, like R and Matlab, and software for brain imaging to
correctly visualise analysis results.

This package aims to make it possible to plot results directly through
R.

## Atlases

There are currently four atlases available in the package:

1.  `dk_3d` - Desikan-Killiany atlas (aparc).  
2.  `aseg_3d` - Automatic sub-cortical segmentation.

If you want to create your own custom atlas or discover other compatible
atlases, please see the companion package
[ggsegExtra](https://lcbc-uio.github.io/ggsegExtra/).

## Installation

The package can be installed using {remotes}. The package includes some
large datasets for the brain coordinates. Please be patient during
download and install, it will take some time.

``` r
install.packages("remotes")
remotes::install_github("LCBC-UiO/ggseg3d", build_vignettes = TRUE)
```

The functions are now installed, and you may load them when you want to
use them. All functions are documented in standard R fashion.

## Use

The package also has a vignette, to help you get started using it. You
can access it
[here](https://lcbc-uio.github.io/ggseg3d/articles/ggseg3d.html), or via
R:

``` r
library(ggseg3d)
vignette("ggseg3d")
```

``` r
p <- ggseg3d(atlas=dk_3d) %>% 
  remove_axes() %>% 
  pan_camera("right lateral")
```

<img src="man/img/README-dk_3d-plot.png" width="700" />

``` r
p <- ggseg3d(atlas=aseg_3d) %>% 
  add_glassbrain() %>% 
  remove_axes() %>% 
  pan_camera("right lateral")
```

<img src="man/img/README-aseg_3d-plot.png" width="700" />

### Report bugs or requests

Don’t hesitate to ask for support using [github
issues](https://github.com/LCBC-UiO/ggseg3d/issues), or requesting new
atlases. While we would love getting help in creating new atlases, you
may also request atlases through the issues, and we will try to get to
it.

# Funding

This tool is partly funded by:

**EU Horizon 2020 Grant:** Healthy minds 0-100 years: Optimising the use
of European brain imaging cohorts (Lifebrain).

**Grant agreement number:** 732592.

**Call:** Societal challenges: Health, demographic change and well-being
