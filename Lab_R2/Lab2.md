Lab2 - Multivariate dataframe example
========================================================
author: Klimov
date: 
autosize: true

Task definition
========================================================

Mostly, we have interested what *predictors* from dataframe cause increasing (have an inference) the variable of interest.

But time to time we didn't know much about nature of our data.

Let's imagine you get dataset named **data_a.csv** and need to perform an overview (or explanatory analisys).

Loading dataset
========================================================

Loading dataframe from file **data_a.csv** ^[It is modified gomez.splitsplit, see ```agriculture``` R package]. Locate it in working directory. To check it, type ```getwd()``` and save it to variable called ```data```.



```r
# If need set right working dir by: setwd("~/Lab_R2")
data <- read.csv("data_a.csv")
```


```r
summary(data)
```

```
       id        rep          nit      m       g          output      
 Min.   :  1.0   R1:45   Min.   :  0   I:45   V1:45   Min.   : 3.132  
 1st Qu.: 34.5   R2:45   1st Qu.: 50   M:45   V2:45   1st Qu.: 5.301  
 Median : 68.0   R3:45   Median : 80   O:45   V3:45   Median : 6.509  
 Mean   : 68.0           Mean   : 76                  Mean   : 6.554  
 3rd Qu.:101.5           3rd Qu.:110                  3rd Qu.: 7.644  
 Max.   :135.0           Max.   :140                  Max.   :10.360  
       x           y     
 Min.   :1   Min.   : 1  
 1st Qu.:3   1st Qu.: 4  
 Median :5   Median : 8  
 Mean   :5   Mean   : 8  
 3rd Qu.:7   3rd Qu.:12  
 Max.   :9   Max.   :15  
```

Check
========================================================

In dataframe we have ```output``` variable.

In data we have different variables (_id_, _rep_, _nit_, _m_, _g_, _output_, _x_ and _y_). How to list them?:


```r
names(data) # return a vector of variable names
```

```
[1] "id"     "rep"    "nit"    "m"      "g"      "output" "x"      "y"     
```

Main symbol of today is tilde
========================================================

When you build more or less complex model in R you will need tilde sign (~). For exmaple linear model have such notation:


```r
lm(weight ~ group) # lm = Linear model
```

Please be free to copy *tilda* from field behind:

```
~
```

Outline
========================================================

- Check data structure (detect types of variables)
- Fix variable types (convert strings to factors)
- Perform correlation
- Plot relationships between variables
- Make lm or ANOVA analysis
- Check interaction between variables

Good final plot may looks like that
========================================================

![Result may looks like this](Result.pdf)
