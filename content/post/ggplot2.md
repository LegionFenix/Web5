---
title: "ggplot2"
author: "Кузьмин"
date: "2023-04-29"
output: html_document
---



## ggplot2

ggplot2 — это система декларативного создания графики.

### Пример точечной диаграммы


```r
library(ggplot2)
```

```
## Warning: пакет 'ggplot2' был собран под R версии 4.2.2
```

```r
ggplot(mtcars, aes(x = wt, y = mpg)) +
  geom_point(color = "blue") +
  ggtitle("Зависимость расхода топлива \n от веса автомобиля") +
  xlab("Вес автомобиля") +
  ylab("Расход топлива")
```

<img src="/post/ggplot2_files/figure-html/point-1.png" width="672" />

### Пример гистограммы


```r
library(ggplot2)
ggplot(mtcars, aes(x = mpg)) +
  geom_histogram(bins = 10, fill = "green", color = "black") +
  xlab("Расход топлива") +
  ylab("Количество автомобилей")
```

<img src="/post/ggplot2_files/figure-html/hist-1.png" width="672" />

### Пример ящика с усами


```r
library(ggplot2)
ggplot(mtcars, aes(x = wt, y = mpg)) +
  geom_boxplot(fill = "green") +
  ggtitle("Зависимость расхода топлива \n от веса автомобиля") +
  xlab("Вес автомобиля") +
  ylab("Расход топлива")
```

```
## Warning: Continuous x aesthetic
## ℹ did you forget `aes(group = ...)`?
```

<img src="/post/ggplot2_files/figure-html/box-1.png" width="672" />
