---
date: "2023-10-26T00:00:00Z"
external_link: ""
image:
  caption: ""
  focal_point: Smart
links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/georgecushen
slides: example
summary: Saya mencoba membuat penyebaran covid-19 menggunakan highcharter dan worldgeojson dan menurut saya tampilannya keren!
tags:
- Visualization
title: Map Penyebaran Covid-19
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>

Untuk membuat map penyebaran data, terlebih dahulu memanggil packages yang dibutuhkan

``` r
# Instal packages

library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.4     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
library(highcharter)
```

    ## Registered S3 method overwritten by 'quantmod':
    ##   method            from
    ##   as.zoo.data.frame zoo

``` r
library(widgetframe)
```

    ## Loading required package: htmlwidgets

Selanjutnya import data covid dan saya menampilkannya menggunakan head() sehingga hanya menampilkan 6 baris pertama saja

``` r
total_case <- read.csv("covid_data.csv")

head(total_case)
```

    ##   X       location total_cases
    ## 1 1    Afghanistan      158059
    ## 2 2         Africa     9904945
    ## 3 3        Albania      209516
    ## 4 4        Algeria      218432
    ## 5 5 American Samoa          11
    ## 6 6        Andorra       23740

Setelah packages dan data sudah siap selanjutnya kita akan membuat visualisasi mapsnya

``` r
map <- highchart() %>%
  hc_add_series_map(worldgeojson, total_case,
                    value = "total_cases",
                    joinBy = c('name','location'),borderColor = "#FAFAFA") %>% 
  hc_add_theme(hc_theme_ffx()) %>% 
  hc_colors(c("darkgreen", "darkred")) %>%
  hc_colorAxis(stops = color_stops()) %>%
  hc_title(text = "Map Penyebaran Covid-19") %>% 
  hc_subtitle(text = "Tanggal Data : 2022-01-01") %>% 
  hc_credits(enabled = T, text = "Made by Harun Deppalallo")

frameWidget(map)
```

<div id="htmlwidget-1" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-3.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>
