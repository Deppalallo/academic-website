---
date: "2023-11-11T00:00:00Z"
external_link: ""
image:
  caption: ""
  focal_point: Smart
links:
- icon: instagram
  icon_pack: fab
  name: Follow
  url: https://www.instagram.com/hd03.00/
slides: example
summary: Analisis Penjualan Buku terlaris Amazon 2009-2019 dan analisis Lagu Billboard The Hot 100.
tags:
- Visualization
title: Buku Terlaris Teratas Amazon 2009 - 2019 dan Lagu "The Hot 100" di Billboard
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>
<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>
<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>
<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>
<script src="{{< blogdown/postref >}}index_files/htmlwidgets/htmlwidgets.js"></script>
<script src="{{< blogdown/postref >}}index_files/pymjs/pym.v1.js"></script>
<script src="{{< blogdown/postref >}}index_files/widgetframe-binding/widgetframe.js"></script>

## Load Packages yang dubutuhkan

``` r
library(flexdashboard)
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
library(gt)
```

    ## Warning: package 'gt' was built under R version 4.3.2

``` r
library(htmltools)
library(viridis)
```

    ## Loading required package: viridisLite

``` r
library(palmerpenguins)
library(widgetframe)
```

    ## Loading required package: htmlwidgets

## Analisis Penjualan Buku terlaris Amazon 2009-2019

##### Tentang Kumpulan Data

Dataset Top 50 buku terlaris Amazon tahun 2009 hingga 2019. Berisi 550 buku, datanya dikategorikan menjadi fiksi dan nonfiksi menggunakan Goodreads

Selanjutnya kita mengimport dataset yang akan digunakan dan menampilkan 10 baris tabel pertama

``` r
book <- read_csv("book.csv")
```

    ## New names:
    ## Rows: 351 Columns: 8
    ## ── Column specification
    ## ──────────────────────────────────────────────────────── Delimiter: "," chr
    ## (3): Name, Author, Genre dbl (5): ...1, User_Rating, Reviews, Price, Year
    ## ℹ Use `spec()` to retrieve the full column specification for this data. ℹ
    ## Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## • `` -> `...1`

``` r
head(book)
```

    ## # A tibble: 6 × 8
    ##    ...1 Name                        Author User_Rating Reviews Price  Year Genre
    ##   <dbl> <chr>                       <chr>        <dbl>   <dbl> <dbl> <dbl> <chr>
    ## 1     1 10-Day Green Smoothie Clea… JJ Sm…         4.7   17350     8  2016 Non …
    ## 2     2 11/22/63: A Novel           Steph…         4.6    2052    22  2011 Fict…
    ## 3     3 12 Rules for Life: An Anti… Jorda…         4.7   18979    15  2018 Non …
    ## 4     4 1984 (Signet Classics)      Georg…         4.7   21424     6  2017 Fict…
    ## 5     5 5,000 Awesome Facts (About… Natio…         4.8    7665    12  2019 Non …
    ## 6     6 A Dance with Dragons (A So… Georg…         4.4   12643    11  2011 Fict…

Kita akan mencari tahu Buku Terpopuler tahun 2009-2019 berdasarkan Review

``` r
# colors
custom_colors <- viridis::turbo(n = 17)

#most popular books by reviews
populer_book <- book %>% 
  arrange(desc(Reviews)) %>% 
  head(17) %>% 
  hchart('bar', hcaes(x = Name, y = Reviews, color = custom_colors)) %>% 
  hc_add_theme(hc_theme_flatdark()) %>% 
  hc_tooltip(pointFormat = '<b> Jumlah Ulasan : </b> {point.y} <br>') %>% 
  hc_title(text = 'Buku Terpopuler dari tahun 2009-2019',
           style = list(fontSize = '25px', fontWeight = 'bold')) %>% 
  hc_subtitle(text = 'Berdasarkan Ulasan (Reviews)',
              style =list(fontSize = '16px')) %>% 
  hc_credits(enabled = TRUE, text = '@deppalallo_harun')
frameWidget(populer_book)
```

<div id="htmlwidget-1" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-3.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>

Kita juga akan mencari tahu Penulis Terpopuler tahun 2009-2019 berdasarkan Review

``` r
# colors
custom_colors <- viridis::plasma(n = 15)

#most popular autors by reviews
populer_author <- book %>% 
  group_by(Author) %>% 
  summarise(Reviews=sum(Reviews)) %>% 
  arrange(desc(Reviews)) %>% 
  head(15) %>% 
  hchart('column', hcaes(x = Author, y = Reviews, color = custom_colors)) %>% 
  hc_add_theme(hc_theme_flatdark()) %>% 
  hc_tooltip(pointFormat = '<b> Jumlah Ulasan : </b> {point.y} <br>') %>% 
  hc_title(text = 'Penulis Terpopuler dari tahun 2009-2019',
           style = list(fontSize = '25px', fontWeight = 'bold')) %>% 
  hc_subtitle(text = 'Berdasarkan Ulasan (Reviews)',
              style = list(fontSize = '16px')) %>% 
  hc_credits(enabled = TRUE, text = '@deppalallo_harun')

frameWidget(populer_author)
```

    ## Warning in dir.create(target_dir): 'highchart_libs\highcharts' already exists

<div id="htmlwidget-2" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-2">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-4.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>

Kita juga akan melihat Kategori Terpopuler tahun 2009-2019 berdasarkan Review

``` r
#colors
custom_colors <- viridis::turbo(n=2)

#Most common gendre

populer_kategori <- book %>% 
  group_by(Genre) %>% 
  summarise(count = n()) %>% 
  hchart('pie', hcaes(x = Genre, y = count, color = custom_colors)) %>% 
  hc_add_theme(hc_theme_flatdark()) %>% 
  hc_tooltip(pointFormat = '<b> Proporsi : </b> {point.percentage:,.2f}%') %>% 
  hc_title(text = 'Genre Terpopuler dari Tahun 2009-2019',
           style = list(fontSize = '15px', fontWeight = 'bold')) %>% 
  hc_credits(enabled = TRUE, text = '@deppalallo_harun')

frameWidget(populer_kategori)
```

<div id="htmlwidget-3" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-3">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-5.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>

##### Tabel Buku terpopuler berdasarkan ulasan pengguna

``` r
#Going to be a dta table

book1 <- book %>% 
  filter(User_Rating >= 4.9) %>% 
  arrange(desc(Reviews)) %>% 
  select(Name, Author)

#HTML table

div(style = 'height:600px; overflow-y:scroll', gt(book1) %>% 
  tab_header(title = md('Buku Terpopuler dari Tahun 2009-2019'),
             subtitle = md('Berdasarkan Ulasan Pengguna')) %>% 
  opt_table_font(font = list(google_font('Chivo'), default_fonts())) %>% 
  tab_style(locations = cells_column_labels(columns = everything()),
            style = list(cell_borders(sides = 'bottom', weight = px(2)),
                         cell_text(weight = 'bold'))) %>%
    tab_options(table.font.size = px(12L),
                table.border.top.style = 'none',
                column_labels.border.bottom.width = 2,
                table_body.border.top.style = 'none',
                data_row.padding = px(3))
)
```

<div style="height:600px; overflow-y:scroll">
<div id="eastjxoosy" style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>@import url("https://fonts.googleapis.com/css2?family=Chivo:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
#eastjxoosy table {
  font-family: Chivo, system-ui, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
&#10;#eastjxoosy thead, #eastjxoosy tbody, #eastjxoosy tfoot, #eastjxoosy tr, #eastjxoosy td, #eastjxoosy th {
  border-style: none;
}
&#10;#eastjxoosy p {
  margin: 0;
  padding: 0;
}
&#10;#eastjxoosy .gt_table {
  display: table;
  border-collapse: collapse;
  line-height: normal;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 12px;
  font-weight: normal;
  font-style: normal;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_caption {
  padding-top: 4px;
  padding-bottom: 4px;
}
&#10;#eastjxoosy .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}
&#10;#eastjxoosy .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 3px;
  padding-bottom: 5px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}
&#10;#eastjxoosy .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}
&#10;#eastjxoosy .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}
&#10;#eastjxoosy .gt_column_spanner_outer:first-child {
  padding-left: 0;
}
&#10;#eastjxoosy .gt_column_spanner_outer:last-child {
  padding-right: 0;
}
&#10;#eastjxoosy .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 5px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}
&#10;#eastjxoosy .gt_spanner_row {
  border-bottom-style: hidden;
}
&#10;#eastjxoosy .gt_group_heading {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  text-align: left;
}
&#10;#eastjxoosy .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}
&#10;#eastjxoosy .gt_from_md > :first-child {
  margin-top: 0;
}
&#10;#eastjxoosy .gt_from_md > :last-child {
  margin-bottom: 0;
}
&#10;#eastjxoosy .gt_row {
  padding-top: 3px;
  padding-bottom: 3px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}
&#10;#eastjxoosy .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#eastjxoosy .gt_stub_row_group {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 5px;
  padding-right: 5px;
  vertical-align: top;
}
&#10;#eastjxoosy .gt_row_group_first td {
  border-top-width: 2px;
}
&#10;#eastjxoosy .gt_row_group_first th {
  border-top-width: 2px;
}
&#10;#eastjxoosy .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#eastjxoosy .gt_first_summary_row {
  border-top-style: solid;
  border-top-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_first_summary_row.thick {
  border-top-width: 2px;
}
&#10;#eastjxoosy .gt_last_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#eastjxoosy .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_last_grand_summary_row_top {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-bottom-style: double;
  border-bottom-width: 6px;
  border-bottom-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}
&#10;#eastjxoosy .gt_table_body {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#eastjxoosy .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}
&#10;#eastjxoosy .gt_sourcenote {
  font-size: 90%;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 5px;
  padding-right: 5px;
}
&#10;#eastjxoosy .gt_left {
  text-align: left;
}
&#10;#eastjxoosy .gt_center {
  text-align: center;
}
&#10;#eastjxoosy .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}
&#10;#eastjxoosy .gt_font_normal {
  font-weight: normal;
}
&#10;#eastjxoosy .gt_font_bold {
  font-weight: bold;
}
&#10;#eastjxoosy .gt_font_italic {
  font-style: italic;
}
&#10;#eastjxoosy .gt_super {
  font-size: 65%;
}
&#10;#eastjxoosy .gt_footnote_marks {
  font-size: 75%;
  vertical-align: 0.4em;
  position: initial;
}
&#10;#eastjxoosy .gt_asterisk {
  font-size: 100%;
  vertical-align: 0;
}
&#10;#eastjxoosy .gt_indent_1 {
  text-indent: 5px;
}
&#10;#eastjxoosy .gt_indent_2 {
  text-indent: 10px;
}
&#10;#eastjxoosy .gt_indent_3 {
  text-indent: 15px;
}
&#10;#eastjxoosy .gt_indent_4 {
  text-indent: 20px;
}
&#10;#eastjxoosy .gt_indent_5 {
  text-indent: 25px;
}
</style>
<table class="gt_table" data-quarto-disable-processing="false" data-quarto-bootstrap="false">
  <thead>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_title gt_font_normal" style>Buku Terpopuler dari Tahun 2009-2019</td>
    </tr>
    <tr class="gt_heading">
      <td colspan="2" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style>Berdasarkan Ulasan Pengguna</td>
    </tr>
    <tr class="gt_col_headings">
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="border-bottom-width: 2px; border-bottom-style: solid; border-bottom-color: #000000; font-weight: bold;" scope="col" id="Name">Name</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1" style="border-bottom-width: 2px; border-bottom-style: solid; border-bottom-color: #000000; font-weight: bold;" scope="col" id="Author">Author</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td headers="Name" class="gt_row gt_left">Oh, the Places You'll Go!</td>
<td headers="Author" class="gt_row gt_left">Dr. Seuss</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Harry Potter and the Chamber of Secrets: The Illustrated Edition (Harry Potter, Book 2)</td>
<td headers="Author" class="gt_row gt_left">J.K. Rowling</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Jesus Calling: Enjoying Peace in His Presence (with Scripture References)</td>
<td headers="Author" class="gt_row gt_left">Sarah Young</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">The Very Hungry Caterpillar</td>
<td headers="Author" class="gt_row gt_left">Eric Carle</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Brown Bear, Brown Bear, What Do You See?</td>
<td headers="Author" class="gt_row gt_left">Bill Martin Jr.</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man: Fetch-22: From the Creator of Captain Underpants (Dog Man #8)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Last Week Tonight with John Oliver Presents A Day in the Life of Marlon Bundo (Better Bundo Book, LGBT Childrens Book)</td>
<td headers="Author" class="gt_row gt_left">Jill Twiss</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Harry Potter and the Sorcerer's Stone: The Illustrated Edition (Harry Potter, Book 1)</td>
<td headers="Author" class="gt_row gt_left">J.K. Rowling</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Wrecking Ball (Diary of a Wimpy Kid Book 14)</td>
<td headers="Author" class="gt_row gt_left">Jeff Kinney</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Strange Planet (Strange Planet Series)</td>
<td headers="Author" class="gt_row gt_left">Nathan W. Pyle</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man: For Whom the Ball Rolls: From the Creator of Captain Underpants (Dog Man #7)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">The Wonderful Things You Will Be</td>
<td headers="Author" class="gt_row gt_left">Emily Winfield Martin</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">The Magnolia Story</td>
<td headers="Author" class="gt_row gt_left">Chip Gaines</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Harry Potter and the Goblet of Fire: The Illustrated Edition (Harry Potter, Book 4) (4)</td>
<td headers="Author" class="gt_row gt_left">J. K. Rowling</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man: Brawl of the Wild: From the Creator of Captain Underpants (Dog Man #6)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Rush Revere and the Brave Pilgrims: Time-Travel Adventures with Exceptional Americans (1)</td>
<td headers="Author" class="gt_row gt_left">Rush Limbaugh</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Goodnight, Goodnight Construction Site (Hardcover Books for Toddlers, Preschool Books for Kids)</td>
<td headers="Author" class="gt_row gt_left">Sherri Duskey Rinker</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Unfreedom of the Press</td>
<td headers="Author" class="gt_row gt_left">Mark R. Levin</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Hamilton: The Revolution</td>
<td headers="Author" class="gt_row gt_left">Lin-Manuel Miranda</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man: Lord of the Fleas: From the Creator of Captain Underpants (Dog Man #5)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">The Legend of Zelda: Hyrule Historia</td>
<td headers="Author" class="gt_row gt_left">Patrick Thorpe</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man and Cat Kid: From the Creator of Captain Underpants (Dog Man #4)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Dog Man: A Tale of Two Kitties: From the Creator of Captain Underpants (Dog Man #3)</td>
<td headers="Author" class="gt_row gt_left">Dav Pilkey</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Rush Revere and the First Patriots: Time-Travel Adventures With Exceptional Americans (2)</td>
<td headers="Author" class="gt_row gt_left">Rush Limbaugh</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Obama: An Intimate Portrait</td>
<td headers="Author" class="gt_row gt_left">Pete Souza</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Harry Potter and the Prisoner of Azkaban: The Illustrated Edition (Harry Potter, Book 3)</td>
<td headers="Author" class="gt_row gt_left">J.K. Rowling</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Humans of New York : Stories</td>
<td headers="Author" class="gt_row gt_left">Brandon Stanton</td></tr>
    <tr><td headers="Name" class="gt_row gt_left">Little Blue Truck</td>
<td headers="Author" class="gt_row gt_left">Alice Schertle</td></tr>
  </tbody>
  &#10;  
</table>
</div>
</div>

## Analisis Lagu “The Hot 100” di Billboard

##### Tentang Kumpulan Data

Billboard Hot 100 adalah tangga rekaman standar industri musik di Amerika Serikat untuk lagu-lagu, yang diterbitkan mingguan oleh majalah Billboard. Pemeringkatan tangga lagu didasarkan pada penjualan, pemutaran radio, dan streaming online di Amerika Serikat.

Setiap minggu, Billboard merilis chart “The Hot 100” yang berisi lagu-lagu yang sedang tren dalam penjualan dan pemutaran pada minggu itu. Kumpulan data ini adalah kumpulan dari semua tangga lagu “The Hot 100” yang dirilis sejak dimulainya pada tahun 1958.

import dataset yang akan digunakan dan menampilkan 10 baris tabel pertama

``` r
song1 <- read_csv("song1.csv")
```

    ## New names:
    ## Rows: 29681 Columns: 4
    ## ── Column specification
    ## ──────────────────────────────────────────────────────── Delimiter: "," chr
    ## (2): song, artist dbl (2): ...1, weeks_on_board
    ## ℹ Use `spec()` to retrieve the full column specification for this data. ℹ
    ## Specify the column types or set `show_col_types = FALSE` to quiet this message.
    ## • `` -> `...1`

``` r
head(song1)
```

    ## # A tibble: 6 × 4
    ##    ...1 song                                      artist          weeks_on_board
    ##   <dbl> <chr>                                     <chr>                    <dbl>
    ## 1     1 "\"B\" Girls"                             Young And Rest…             15
    ## 2     2 "\"Cherry Cherry\" from Hot August Night" Neil Diamond                10
    ## 3     3 "\"Having A Party\" Medley"               The Ovations (…              9
    ## 4     4 "\"Joy\" Pt. I"                           Isaac Hayes                  9
    ## 5     5 "\"Roots\" Medley"                        Quincy Jones                 7
    ## 6     6 "\"Yep!\""                                Duane Eddy His…              9

##### Lagu Terpopuler di Billboard

``` r
#colors
custom_colors <- viridis::plasma(n =20)

# most popular author by weeks on board
populer_song <- song1 %>% 
  arrange(desc(weeks_on_board)) %>% 
  head(20) %>% 
  hchart('lollipop', hcaes(x = song, y = weeks_on_board, color = custom_colors)) %>% 
  hc_add_theme(hc_theme_flatdark()) %>% 
  hc_tooltip(pointFormat = '<b> Number of weeks on board : </b> {point.y} <br>') %>%
  hc_yAxis(text = list('Weeks on Board')) %>% 
  hc_xAxis(text = list(text = 'Songs')) %>% 
  hc_title(text = 'Lagu Terpopuler',
           style = list(fontSize = '25px', fontWeight = 'bold')) %>% 
  hc_subtitle(text = 'Berdasarkan (Weeks on Board)',
              style = list(fontSize = '16px')) %>% 
  hc_credits(enabled = TRUE, text = '@deppalallo_harun')
frameWidget(populer_song)
```

    ## Warning in dir.create(target_dir): 'highchart_libs\highcharts' already exists

<div id="htmlwidget-4" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-4">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-8.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>

##### Artis Terpopuler di Billboard

``` r
#colors
custom_colors <- viridis::turbo(n=10)

#Most common gendre

populer_artists <- song1 %>% 
  group_by(artist) %>% 
  summarise(weeks_on_board=sum(weeks_on_board)) %>% 
  arrange(desc(weeks_on_board)) %>% 
  head(10) %>% 
  hchart('pie', hcaes(x = artist, y = weeks_on_board, color = custom_colors)) %>% 
  hc_add_theme(hc_theme_flatdark()) %>% 
  hc_tooltip(pointFormat = '<b> Number of weeks on board : </b> {point.y} <br>') %>% 
  hc_title(text = 'Artis Terpopuler',
           style = list(fontSize = '25px', fontWeight = 'bold')) %>% 
  hc_subtitle(text = 'Berdasarkan Weeks on Board',
                          style = list(fontSize = '16px')) %>% 
  hc_credits(enabled = TRUE, text = '@deppalallo_harun')
frameWidget(populer_artists)
```

<div id="htmlwidget-5" style="width:100%;height:480px;" class="widgetframe html-widget "></div>
<script type="application/json" data-for="htmlwidget-5">{"x":{"url":"index_files/figure-html//widgets/widget_unnamed-chunk-9.html","options":{"xdomain":"*","allowfullscreen":false,"lazyload":false}},"evals":[],"jsHooks":[]}</script>
