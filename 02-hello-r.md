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

Calculate 2 to the power of 8?

``` r
# Exponentiation
```

Variable assignment
-------------------

A basic concept in (statistical) programming is called a **variable**.

A variable allows you to store a value (e.g. 4) or an object (e.g. a function description) in R. You can then later use this variable's name to easily access the value or the object that is stored within this variable.

You can assign a value 4 to a variable `my_var` with the command:

``` r
my_var <- 4
```

Please complete this code by assigning value 42 to variable x (but first you can try to run this code chunk as it is. What is R complaining about?):

``` r
# Assign the value 42 to x
x <- 

# Print out the value of the variable x
x
```

`Error: object 'x' not found` means that object with name x does not exists. Have a look at your Environment. Do you see object x? You can only create objects by assigning them some value(s) or even empty structure.

> Note that `<-` is the assignment operator in R

Suppose you want to calculate your body mass index. Body mass index (BMI) is calculated from height in m and weight in kg using following formula:

$$BMI = \\frac{height\_{kg}}{weight\_m^2}$$

You want to store your body weight in a variable with the name my\_weight. Type the following code into chunk: `my_weight <- 99` (replace 99 with your body weight). This will assign the value of your body weight to my\_apples.

``` r
# assign your weight to variable my_weight
```

Type: my\_weight into chunk below. This will print out the value of my\_weight:

``` r
# type: my_weight
```

BMI formula also needs height. Please create also the variable **my\_height** and assign the value of your height in meters to it:

``` r
# create variable my_height with your height in meters
```

Next, you can calculate your body mass index. Since you have given meaningful names to these values, you can now code this in a clear way `my_weight / my_height^2`

Calculate BMI and have R simply print the result.

In order to use calculated BMI value in downstream analyses or visualizations you need to assign it to a new variable, let's call it my\_bmi. Assign the result of BMI calculation to a new variable my\_bmi.

The big advantage of doing calculations with variables is reusability. If you just change my\_weight to equal 45 instead of 99, or whatever your body weight is, and rerun the script, my\_bmi will automatically update as well.

The + operator works with numeric variables in R. If you really tried to calculate BMI using "weight" and "height", and assigned a text value to the variable my\_weight (see the chunk below), you would be trying to assign the calculation using of a numeric and a character variable to the variable my\_height. This is not possible!

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
-   Text (or string) values are called characters.

``` r
# Change my_numeric to be 42
my_numeric <- 42.5

# Change my_character to be "universe"
my_character <- "some text"

# Change my_logical to be FALSE
my_logical <- TRUE
```

Note how the quotation marks on the chunk above indicate that "some text" is a character.

### What's that data type?

When you tried to calculate BMI using my\_weight with value "forty five", you got an error due to a mismatch in data types. You can avoid such annoying situations by checking the data type of a variable beforehand. You can do this with the class() function, as the code below shows.

``` r
# Declare variables of different types
my_numeric <- 42
my_character <- "universe"
my_logical <- FALSE 

# Check class of my_numeric
class(my_numeric)

# Check class of my_character


# Check class of my_logical
```