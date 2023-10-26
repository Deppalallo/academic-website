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
summary: An example of visualization Penguins data using ggplot2 package.
tags:
- Deep Learning
title: Ggplot
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

This blog post will teach you how to create a ggplot using an open-source dataset called "penguins"

Instal package


```r
library(palmerpenguins)
library(highcharter)
```

```
## Registered S3 method overwritten by 'quantmod':
##   method            from
##   as.zoo.data.frame zoo
```

```r
library(ggplot2)
```

Let's take a brief at the dataset using the head function

```r
head(penguins)
```

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
```

Now we can create the scatter

```r
na.omit(penguins) %>% 
  ggplot(aes(bill_length_mm, bill_depth_mm, color = species))+
  geom_point()
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-3-1.png" width="672" />

