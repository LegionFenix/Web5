---
title: "leaflet.extras"
author: "Кузьмин"
date: "2023-04-29"
output: html_document
---

<script src="/rmarkdown-libs/htmlwidgets/htmlwidgets.js"></script>
<script src="/rmarkdown-libs/jquery/jquery.min.js"></script>
<link href="/rmarkdown-libs/leaflet/leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet/leaflet.js"></script>
<link href="/rmarkdown-libs/leafletfix/leafletfix.css" rel="stylesheet" />
<script src="/rmarkdown-libs/proj4/proj4.min.js"></script>
<script src="/rmarkdown-libs/Proj4Leaflet/proj4leaflet.js"></script>
<link href="/rmarkdown-libs/rstudio_leaflet/rstudio_leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet-binding/leaflet.js"></script>
<script src="/rmarkdown-libs/lfx-bouncemarker/lfx-bouncemarker-prod.js"></script>
<script src="/rmarkdown-libs/lfx-bouncemarker/lfx-bouncemarker-bindings.js"></script>
<script src="/rmarkdown-libs/htmlwidgets/htmlwidgets.js"></script>
<script src="/rmarkdown-libs/jquery/jquery.min.js"></script>
<link href="/rmarkdown-libs/leaflet/leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet/leaflet.js"></script>
<link href="/rmarkdown-libs/leafletfix/leafletfix.css" rel="stylesheet" />
<script src="/rmarkdown-libs/proj4/proj4.min.js"></script>
<script src="/rmarkdown-libs/Proj4Leaflet/proj4leaflet.js"></script>
<link href="/rmarkdown-libs/rstudio_leaflet/rstudio_leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet-binding/leaflet.js"></script>
<link href="/rmarkdown-libs/lfx-pulse-icon/lfx-pulse-icon-prod.css" rel="stylesheet" />
<script src="/rmarkdown-libs/lfx-pulse-icon/lfx-pulse-icon-prod.js"></script>
<script src="/rmarkdown-libs/lfx-pulse-icon/lfx-pulse-icon-bindings.js"></script>
<script src="/rmarkdown-libs/htmlwidgets/htmlwidgets.js"></script>
<script src="/rmarkdown-libs/jquery/jquery.min.js"></script>
<link href="/rmarkdown-libs/leaflet/leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet/leaflet.js"></script>
<link href="/rmarkdown-libs/leafletfix/leafletfix.css" rel="stylesheet" />
<script src="/rmarkdown-libs/proj4/proj4.min.js"></script>
<script src="/rmarkdown-libs/Proj4Leaflet/proj4leaflet.js"></script>
<link href="/rmarkdown-libs/rstudio_leaflet/rstudio_leaflet.css" rel="stylesheet" />
<script src="/rmarkdown-libs/leaflet-binding/leaflet.js"></script>
<script src="/rmarkdown-libs/lfx-geodesic/lfx-geodesic-prod.js"></script>
<script src="/rmarkdown-libs/lfx-geodesic/lfx-geodesic-bindings.js"></script>

## Функции пакета leaflet.extras

Пакет предоставляющий дополнительную функциональность пакету leaflet R с использованием различных плагинов

### Функция addBounceMarkers

``` r
library(leaflet.extras)
```

    ## Warning: пакет 'leaflet.extras' был собран под R версии 4.2.2

    ## Загрузка требуемого пакета: leaflet

    ## Warning: пакет 'leaflet' был собран под R версии 4.2.2

``` r
leaflet() %>%
  addTiles() %>%
  addBounceMarkers(40, 70, duration = 10000, height = 100)
```

<div class="leaflet html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-1" style="width:672px;height:480px;"></div>
<script type="application/json" data-for="htmlwidget-1">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"https://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"https://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addBounceMarkers","args":[40,70,10000,100]}]},"evals":[],"jsHooks":[]}</script>

### Функция addPulseMarkers

``` r
library(leaflet.extras)
leaflet() %>%
  addTiles() %>%
  addPulseMarkers(
    lng = -118.456554, lat = 34.078039,
    label = "This is a label",
    icon = makePulseIcon(heartbeat = 0.9))
```

<div class="leaflet html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-2" style="width:672px;height:480px;"></div>
<script type="application/json" data-for="htmlwidget-2">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"https://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"https://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addPulseMarkers","args":[34.078039,-118.456554,{"color":"#ff0000","iconSize":12,"animate":true,"heartbeat":0.9},null,null,{"interactive":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},null,null,null,null,"This is a label",null]}],"limits":{"lat":[34.078039,34.078039],"lng":[-118.456554,-118.456554]}},"evals":[],"jsHooks":[]}</script>

### Функция addGeodesicPolylines

``` r
library(leaflet.extras)
berlin <- c(52.51, 13.4)
losangeles <- c(34.05, -118.24)
santiago <- c(-33.44, -70.71)
tokio <- c(35.69, 139.69)
sydney <- c(-33.91, 151.08)
capetown <- c(-33.91, 18.41)
calgary <- c(51.05, -114.08)
hammerfest <- c(70.67, 23.68)
barrow <- c(71.29, -156.76)
df <- as.data.frame(rbind(hammerfest, calgary, losangeles, santiago, capetown, tokio, barrow))
names(df) <- c("lat","lng")
leaflet(df) %>%
  addTiles() %>%
  addGeodesicPolylines(lng = ~lng, lat = ~lat, weight = 4, color = "red",
                       steps = 100) %>%
  addCircleMarkers(df, lat = ~lat,lng = ~lng, radius = 3, stroke = FALSE,
                   fillColor = "black", fillOpacity = 5)
```

<div class="leaflet html-widget html-fill-item-overflow-hidden html-fill-item" id="htmlwidget-3" style="width:672px;height:480px;"></div>
<script type="application/json" data-for="htmlwidget-3">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":1,"detectRetina":false,"attribution":"&copy; <a href=\"https://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"https://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addGeodesicPolylines","args":[[[[{"lng":[23.68,-114.08,-118.24,-70.71,18.41,139.69,-156.76],"lat":[70.67,51.05,34.05,-33.44,-33.91,35.69,71.29]}]]],null,null,{"interactive":true,"className":"","steps":100,"wrap":true,"stroke":true,"color":"red","weight":4,"opacity":0.5,"dashArray":null,"smoothFactor":1,"noClip":false},null,null,null,null,null]},{"method":"addCircleMarkers","args":[[70.67,51.05,34.05,-33.44,-33.91,35.69,71.29],[23.68,-114.08,-118.24,-70.71,18.41,139.69,-156.76],3,{"lat":[70.67,51.05,34.05,-33.44,-33.91,35.69,71.29],"lng":[23.68,-114.08,-118.24,-70.71,18.41,139.69,-156.76]},null,{"interactive":true,"className":"","stroke":false,"color":"#03F","weight":5,"opacity":0.5,"fill":true,"fillColor":"black","fillOpacity":5},null,null,null,null,null,{"interactive":false,"permanent":false,"direction":"auto","opacity":1,"offset":[0,0],"textsize":"10px","textOnly":false,"className":"","sticky":true},null]}],"limits":{"lat":[-33.91,71.29],"lng":[-156.76,139.69]}},"evals":[],"jsHooks":[]}</script>
