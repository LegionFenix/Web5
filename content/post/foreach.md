---
title: "foreach"
author: "Кузьмин"
date: "2023-04-29"
output: html_document
---



## Оптимизация вычислений с использованием функций пакета foreach

Пакет foreach предоставляет конструкцию цикла для повторного выполнения R-кода.Основная причина использования пакета foreach заключается в том, что он поддерживает параллельное выполнение.

### Общая конструкция


```r
library(foreach)
```

```
## Warning: пакет 'foreach' был собран под R версии 4.2.2
```

```r
x <- foreach(i=1:3) %do% sqrt(i)
x
```

```
## [[1]]
## [1] 1
## 
## [[2]]
## [1] 1.414214
## 
## [[3]]
## [1] 1.732051
```
### Параллельное вычисление
Параллельное вычисление осуществляется с помощью пакета "doParallel"


```r
library(doParallel)
```

```
## Warning: пакет 'doParallel' был собран под R версии 4.2.2
```

```
## Загрузка требуемого пакета: iterators
```

```
## Warning: пакет 'iterators' был собран под R версии 4.2.2
```

```
## Загрузка требуемого пакета: parallel
```

```r
library(foreach)

cl <- makeCluster(4)    # Создаем кластер на четыре потоков
registerDoParallel(cl)  # Регистрируем кластер

system.time({
  foreach(i=1:8) %dopar% Sys.sleep(1) # останавливаем цикл на секунду
})
```

```
## пользователь      система       прошло 
##          0.0          0.0          2.1
```

```r
stopCluster(cl)
```
