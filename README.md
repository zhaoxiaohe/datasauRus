
<!-- README.md is generated from README.Rmd. Please edit that file -->
datasauRus
==========

[![Build Status](https://travis-ci.org/stephlocke/datasauRus.svg?branch=master)](https://travis-ci.org/stephlocke/datasauRus)

This package wraps the awesome Datasaurus Dozen dataset.

The Datasaurus was created by Alberto Cairo in this great [blog post](http://www.thefunctionalart.com/2016/08/download-datasaurus-never-trust-summary.html).

Datasaurus shows us why visualisation is important, not just summary statistics.

He's been subsequently made even more famous in the paper [Same Stats, Different Graphs: Generating Datasets with Varied Appearance and Identical Statistics through Simulated Annealing](https://www.autodeskresearch.com/publications/samestats) by Justin Matejka and George Fitzmaurice.

In the paper, Jusitn and George simulate a variety of datasets that the same summary statistics to the Datasaurus but have very different distributions.

![](https://github.com/stephlocke/lazyCDN/blob/master/DinoSequential.gif?raw=true)

This package looks to make these datasets available for use as an advanced [Anscombe's Quartet](https://en.wikipedia.org/wiki/Anscombe%27s_quartet), available in R as `anscombe`.

Install
-------

Currently, only available on GitHub, so use `devtools` to install the package

``` r
devtools::install_github("stephlocke/datasauRus")
```

Usage
-----

You can use the package to produce Anscombe plots and more.

``` r
library(ggplot2)
library(datasauRus)
ggplot(datasaurus_dozen, aes(x=x, y=y, colour=dataset))+
  geom_point()+
  theme_void()+
  theme(legend.position = "none")+
  facet_wrap(~dataset, ncol=3)
```

![](README/README-unnamed-chunk-2-1.png)

Tests
-----

``` r
library(devtools)
test()
#> Loading datasauRus
#> Loading required package: testthat
#> Testing datasauRus
#> datasets: ......................
#> Raw files: .
#> 
#> DONE ======================================================================
```
