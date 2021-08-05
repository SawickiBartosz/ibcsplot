
<!-- README.md is generated from README.Rmd. Please edit that file -->

# ibcsplot

<!-- badges: start -->

<!-- badges: end -->

The goal of ibcsplot is to enable R users to create charts inspired by
[International Business Communication Standards
(IBCS)](https://www.ibcs.com/). The plots are generated in SVG format,
so embedding them in HTML documents is straight forward.

## Installation

~~You can install the released version of ibcsplot from
[CRAN](https://CRAN.R-project.org) with:~~ The package is going to be
deployed to CRAN, so that the installation process will look like:

``` r
install.packages("ibcsplot")
```

But for now only development version from [GitHub](https://github.com/)
can be installed with:

``` r
# install.packages("devtools")
devtools::install_github("SawickiBartosz/ibcsplot")
```

## Example

How to create IBCS inspired charts using ibcsplot?

``` r
library(ibcsplot) # load the package

# create some data to visualize
df <- data.frame(months = month.abb[1:6],
                 values = round(5 + sin(1:6), 2))

column_chart(df, x = 'months', series = 'values') %>% 
  # create chart in a form of character vector containing SVG content
  SVGrenderer() # render and show the SVG 
```

![example column
chart](https://raw.githubusercontent.com/SawickiBartosz/ibcsplot/main/man/figures/README-example-columns-1.svg)

You can easily create other type of plots, ie. lineplots:

``` r
line_plot(df, cat = df$months, series = 'values', series_labels = 'values') %>% 
  SVGrenderer()
```

![example line chart](man/figures/README-example-lines-1.svg)
