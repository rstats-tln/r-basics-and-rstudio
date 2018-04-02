Hello R
================
Taavi Päll
26 3 2018

Credit: @jennybc, @datacamp

R basics and Rstudio
--------------------

-   Launch RStudio
-   Notice the default panes:
    -   This document (upper left)
    -   Console (lower left)
    -   Environment/History (tabbed in upper right)
    -   Files/Plots/Packages/Help (tabbed in lower right)

R as calculator
---------------

In its most basic form, R can be used as a simple calculator. Consider the following arithmetic operators:

-   Addition: +
-   Subtraction: -
-   Multiplication: \*
-   Division: /
-   Exponentiation: ^
-   Modulo: %%
-   Integer division: %/%

``` r
# An addition
5 + 5
```

``` r
# A subtraction
5 - 5 
```

``` r
# A multiplication
3 * 5
```

``` r
# A division
(5 + 5) / 2
```

### Exercise

1.  Calculate 2 to the power of 8?

``` r
2 ^ 8
```

Variable assignment
-------------------

A basic concept in (statistical) programming is called a **variable**.

A variable allows you to store a value (e.g. 4) or an object (e.g. a function description) in R. You can then later use this variable's name to easily access the value or the object that is stored within this variable.

You can assign a value 4 to a variable `a` with the command:

``` r
a <- 4
```

### Excercise

1.  Please complete this code by assigning value 42 to variable x (but first you can try to run this code chunk as it is. What is R complaining about?):

``` r
# Assign the value 42 to x
x <- 42

# Print out the value of the variable x
x
```

`Error: object 'x' not found` means that object with name x does not exists. Have a look at your Environment. Do you see object x? You can only create objects by assigning them some value(s) or even empty structure.

``` r
y <- vector()
y
```

> Note that `<-` is the assignment operator in R

1.  Suppose you want to calculate **body mass index**.

Body mass index (BMI) is calculated from height in m and weight in kg using following formula:

$$BMI = \\frac{weight\_{kg}}{height\_m^2}$$

You want to store your body weight in a variable with the name my\_weight.

Type the following code into chunk: `my_weight <- 99` (replace 99 with your body weight).

This will assign the value of your body weight to my\_weight.

``` r
# assign your weight to variable my_weight
my_weight <- 73
```

Type: my\_weight into chunk below. This will print out the value of my\_weight:

``` r
# type: my_weight
my_weight
```

BMI formula also needs height.

Please create also the variable **my\_height** and assign the value of your height in meters to it:

``` r
# create variable my_height with your height in meters
my_height <- 1.7
```

Next, you can calculate your body mass index. Since you have given meaningful names to these values, you can now code this in a clear way `my_weight / my_height^2`

Calculate BMI and have R simply print the result.

``` r
my_weight / my_height ^ 2
```

In order to use calculated BMI value in downstream analyses or visualizations you need to assign it to a new variable, let's call it my\_bmi.

Assign the result of BMI calculation to a new variable my\_bmi.

``` r
my_bmi <- my_weight / my_height ^ 2
my_bmi
```

Where am I with my body mass index compared to general population?

``` r
# Mean BMI in Estonia in 40-44 age group is 27.0 for males and 26.5 females. Sd is ~ 6
mean_bmi <- 27
sd_bmi <-  6
# prob. of smaller values
pnorm(my_bmi, mean_bmi, sd_bmi)
# prob. of larger values
pnorm(my_bmi, mean_bmi, sd_bmi, lower.tail = FALSE)
```

It appears that ~39% of males have smaller BMI than me and ~61% have higher BMI than me..

Let's put my number onto plot:

``` r
set.seed(123)
hist(rnorm(1000, mean_bmi, sd_bmi), 30)
abline(v = my_bmi, lty = "dashed")
```

> The big advantage of doing calculations with variables is reusability.

If you just change my\_weight to equal 45 instead of 99, or whatever your body weight is, and rerun the script, my\_bmi will automatically update as well.

The + operator works with numeric variables in R.

If you really tried to calculate BMI using "weight" and "height", and assigned a text value to the variable my\_weight (see the chunk below), you would be trying to assign the calculation using of a numeric and a character variable to the variable my\_height. This is not possible!

``` r
my_weight <- "forty five"
```

``` r
my_bmi <- my_weight / (my_height^2)
```

Try to fix this code above.

Basic data types in R
---------------------

R works with numerous data types. Some of the most basic types to get started are:

-   Decimals values like 4.5 are called numerics.

-   Natural numbers like 4 are called integers. Integers are also numerics.

-   Boolean values (TRUE or FALSE) are called logical.

``` r
TRUE + TRUE
FALSE + TRUE
T + F
```

-   Text (or string) values are called characters.

``` r
# Change my_numeric to be 42
my_numeric <- 42

# Change my_character to be "universe"
my_character <- "universe"
z <- 'and everything'
v <- '"universe" and everything'

# Change my_logical to be FALSE
my_logical <- FALSE
```

``` r
pi
```

Note how the quotation marks on the chunk above indicate that "some text" is a character.

### What's that data type?

When you tried to calculate BMI using my\_weight with value "forty five", you got an error due to a mismatch in data types.

You can avoid such annoying situations by checking the data type of a variable beforehand.

You can do this with the class() function, as the code below shows.

``` r
# Declare variables of different types
my_numeric <- 42
my_character <- "universe"
my_logical <- FALSE 

# Check class of my_numeric
class(my_numeric)

# Check class of my_character
class(my_character)

# Check class of my_logical
class(my_logical)
```

Data structures
---------------

vector and matrix can contain only one type of values: either numerics, booleans, strings - vector - matrix

Different types are coerced into one type

``` r
c(1, "a")
c(T, 1)
c(F, "a")
```

``` r
v <- 1:10
v
class(v)
```

``` r
letters
LETTERS
```

``` r
month.abb
```

``` r
f <- rnorm(1000)
mean(f)
sd(f)
```

``` r
fm <- matrix(f, ncol = 4)
```

``` r
df <- data.frame(months = month.abb, values = rnorm(12))
```

``` r
df[5, 1]
```

``` r
mylist <- list(df, fm, f)
```
