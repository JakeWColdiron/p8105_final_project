Data Processing and Exploratory analyses
================
Jake W. Coldiron,Zixuan Qiu,Tianyuan Deng,Aung Nay Win,Yuqi Cheng

**Date:** 2023-11-10

``` r
library(tidyverse)
library(rvest)
library(httr)
library(plotly)
```

# Data processing

``` r
#input the New York HIV data from NYC opendata 
nyc_HIV1=
  GET("https://data.cityofnewyork.us/resource/ykvb-493p.csv",
  query = list("$limit" = 10000)) |>
  content("parsed")|>
  filter(year >= 2017)
```

    ## Warning: One or more parsing issues, call `problems()` on your data frame for details,
    ## e.g.:
    ##   dat <- vroom(...)
    ##   problems(dat)

``` r
nyc_HIV2=
  GET("https://data.cityofnewyork.us/resource/dxnu-p2qd.csv",
  query = list("$limit" = 22000)) |>
  content("parsed")|>
  filter(year >= 2017)
```

``` r
#HIV service resource 
HIV_service=
  GET("https://data.cityofnewyork.us/resource/pwts-g83w.csv",
  query = list("$limit" = 1000)) |>
  content("parsed")|>
  select(unique_id,facilityname,service_type, address,borough,state,zipcode,latitude,longitude)
```

**A short clear description of where and how data were obtained. explain
the variables means in the data** **Calculate the sum, mean, median,
standard deviation of HIV/AIDS indicators**

# Visualizations

**Shows the number of HIV/AIDS diagnoses by race, sex, and age group.**

``` r
#work
```

summary: **Show the map of NYC HIV service resources location.**

``` r
#work
```

summary:

**Show the distribution of the HIV/AIDS diagnoses by neighborhood.**

``` r
#work
```

summary:

**Trend analysis:analyze the trend of the number of HIV/AIDS diagnoses
over time.**

``` r
#work
```

summary:

# Exploratory statistical analyses.

**Correlation analysis:After the Visualizations is there any association
between different variables such as neighborhood, age, gender, and
race.**

``` r
#work
```

T-test /ANOVA: Compare differences in HIV between two or more groups (
gender or racial). Chi-square test: Analyze associations between
categorical variables (gender, race).
