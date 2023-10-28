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
summary: An example of visualization Penguins data using highcharter package.
tags:
- Visualization
title: Highcharter
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>

This blog post will teach you how to create a highcharter using an open-source dataset called “penguins”

Let’s take a brief at the dataset using the head function

``` r
head(penguins)
```

    ## # A tibble: 6 × 8
    ##   species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
    ##   <fct>   <fct>              <dbl>         <dbl>             <int>       <int>
    ## 1 Adelie  Torgersen           39.1          18.7               181        3750
    ## 2 Adelie  Torgersen           39.5          17.4               186        3800
    ## 3 Adelie  Torgersen           40.3          18                 195        3250
    ## 4 Adelie  Torgersen           NA            NA                  NA          NA
    ## 5 Adelie  Torgersen           36.7          19.3               193        3450
    ## 6 Adelie  Torgersen           39.3          20.6               190        3650
    ## # ℹ 2 more variables: sex <fct>, year <int>

Now we can create the scatter plot between bill_length_mm and bill_length_mm

``` r
scatter_plot  <- na.omit(penguins) %>% 
  hchart("scatter", hcaes(x = bill_length_mm, y = bill_depth_mm, group = species)) %>% 
  hc_add_theme(hc_theme_google()) %>% 
  hc_title(text = "Scatter Plot data Penguins",
           style = list(fontSize = "25px", fontWeight = "bold")) %>% 
  hc_subtitle(text = "By Bill Length (mm) and Bill Depth (mm)",
              style = list(fontSize = "16px")) %>% 
  hc_tooltip(pointFormat = "<b> Bill Length (mm) : </b> {point.x} <br> <b> Bill Depth (mm): </b> {point.y} <br>") %>% 
  hc_credits(enabled = TRUE, text = "@harun_deppalallo")

frameWidget(scatter_plot)
```

<div id="htmlwidget-1" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-3.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>
