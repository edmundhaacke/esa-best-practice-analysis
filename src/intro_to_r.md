# Introduction to R

## Introduction

This is not meant to be a comprehensive guide to learning R, rather it is intended to introduce basic concepts. You can find indepth training provided by the NHS-R community.

## Data Types

R has a number of basic data types:

- character e.g. `"hello"`
- numeric (real/decimal) e.g. `1.1` or `1`
- integer e.g. `1L` where `L` tells R to store as an integer
- logical e.g. `TRUE` or `FALSE`
- complex e.g. `1+4i`, these are complex numbers with real and imaginary parts

Some useful functions to examine the features of objects, not those limited to the aforementioned ones are

- The name of the class(es) from which an object inherits (e.g. what kind of object it is)
    ```r
    helloStr <- "hello, world"
    class(helloStr)
    ```
- The name of the R type an object is
    ```r
    typeof(helloStr)
    ```
- The length of an object
    ```r
    length(helloStr)
    ```
- Any metadata associated with the object
    ```r
    attributes(helloStr)
    ```

### Strings or characters

Strings can be created using either `"` or `'` and are stored as a `character` object.

```r
string1 <- "hello this is a string"
string2 <- 'hello this is also a string'
```

If you require a `'` within a string, for example when defining an SQL query, use `"` to define your string, and vice-versa.

```r
string3 <- "select * from tbl where date >='2022-01-01'"
```

## Data Structures

R also has multiple data structures, including

- atomic vectors e.g. `c(1,2,3,4,5)`
- list e.g. `list(1,"2","three")`
- matrix
- data.frame
- factors

### Atomic vectors

An atomic vector is a vector containing objects all of the same type. If you define an atomic vector with multiple different data types, R will (implicitly) coerce the elements within your vector.

## Loops

```r
for (i in 1:10){
    print(i)
}
```

Another way of looping through a list/vector is to use `lapply(x,FUN,...)`, which applies a function (`FUN`) to a list (or vector) `x`, returning a list of the same length as `x`.

```r
# multiply numbers 1 thru 10 by 100
listOneToTen <- lapply(1:10,function(x) x*100)
# lists can be simplified to a vector using the unlist function
vecOneToTen <- unlist(listOneToTen)
```

The `lapply` function is frequently used within `data.table` to apply a function to several columns, and can be used in aggregation.

```r
# given a data.table dt, substitute all spaces with blanks, and convert to numeric
# for column1 and column2, and place in a new column suffixed with _clean
dt[,c("column1_clean","column2_clean"):=lapply(.SD,function(x){
    tmp <- gsub("[[:blank:]]","",x)
    return(as.numeric(tmp))
}), .SDcols=c("column1","column2")]
# ---- aggregate numeric columns ----
# identify numeric columns by applying is.numeric function to all columns in dt
numCols <- colnames(dt)[unlist(lapply(dt,is.numeric))]
# sum all values in numeric columns
dtAgg <- dt[,lapply(.SD,sum,na.rm=TRUE),by="org_code",.SDcols=numCols]
```