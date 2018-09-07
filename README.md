# style-guide
Exercise the style guides here. Someone other than you will be reviewing your work. Style guides are coding etiquette.

- [R Style Guide](#r-style-guide)
- [Python Style Guide](#python-style-guide)



# R Style Guide

This Style Guideline, in many parts, is referencing Google's R Style Guide and CMU (names, alignment, locality, and comments) coding guidelines. For more details visit:
- [Google R Style Guide](https://google.github.io/styleguide/Rguide.xml)
- [CMU Code Style](https://www.cs.cmu.edu/~pattis/15-1XX/15-200/lectures/style/lecture.html)
- [CMU Code Style](http://www.cs.cmu.edu/~./213/codeStyle.html)


### Summary: R Style Rules
* [File Names](#11-file-names): end in .R
* [Identifiers](#12-identifiers): variable.name (or variableName), FunctionName, kConstantName
* [Line Length](#21-line-length): maximum 80 characters
* [Indentation](#22-Indentation): two spaces, no tabs
* Spacing
* Curly Braces: first on same line, last on own line
* else: Surround else with braces
* Assignment: use <-, not =
* Semicolons: don't use them
* General Layout and Ordering
* Commenting Guidelines: all comments begin with # followed by a space; inline comments need two spaces before the #
* Function Definitions and Calls
* Function Documentation
* Example Function
* TODO Style: TODO(username)

## 1 Notation and Naming

### 1.1 File Names
File names should end in .R and, of course, be meaningful.
```sh
GOOD: predict_ad_revenue.R
BAD: foo.R
```

### 1.2 Identifiers
Don't use underscores ( _ ) or hyphens ( - ) in identifiers. Identifiers should be named according to the following conventions. The preferred form for variable names is all lower case letters and words separated with dots (variable.name), but variableName is also accepted; function names have initial capital letters and no dots (FunctionName); constants are named like functions but with an initial k.

variable.name is preferred, variableName is accepted
```sh
GOOD: avg.clicks
OK: avgClicks
BAD: avg_Clicks
FunctionName
GOOD: CalculateAvgClicks
BAD: calculate_avg_clicks , calculateAvgClicks
Make function names verbs.
Exception: When creating a classed object, the function name (constructor) and class should match (e.g., lm).
kConstantName
```
## 2 Syntax
### 2.1 Line Length
The maximum line length is 80 characters.

### 2.2 Indentation
When indenting your code, use two spaces. Never use tabs or mix tabs and spaces.
Exception: When a line break occurs inside parentheses, align the wrapped line with the first character inside the parenthesis.


### 2.3 Spacing
Place spaces around all binary operators (=, +, -, <-, etc.).
Exception: Spaces around ='s are optional when passing parameters in a function call.

Do not place a space before a comma, but always place one after a comma.


GOOD:
```sh
tab.prior <- table(df[df$days.from.opt < 0, "campaign.id"])
total <- sum(x[, 1])
total <- sum(x[1, ])
```
BAD:
```sh
tab.prior <- table(df[df$days.from.opt<0, "campaign.id"])  # Needs spaces around '<'
tab.prior <- table(df[df$days.from.opt < 0,"campaign.id"])  # Needs a space after the comma
tab.prior<- table(df[df$days.from.opt < 0, "campaign.id"])  # Needs a space before <-
tab.prior<-table(df[df$days.from.opt < 0, "campaign.id"])  # Needs spaces around <-
total <- sum(x[,1])  # Needs a space after the comma
total <- sum(x[ ,1])  # Needs a space after the comma, not before
```

Place a space before left parenthesis, except in a function call.


GOOD:
if (debug)


BAD:

if(debug)

Extra spacing (i.e., more than one space in a row) is okay if it improves alignment of equals signs or arrows (<-).
```sh
plot(x    = x.coord,
     y    = data.mat[, MakeColName(metric, ptiles[1], "roiOpt")],
     ylim = ylim,
     xlab = "dates",
     ylab = metric,
     main = (paste(metric, " for 3 samples ", sep = "")))
```


Do not place spaces around code in parentheses or square brackets.
Exception: Always place a space after a comma.

GOOD:

if (debug)
x[1, ]

BAD:

if ( debug )  # No spaces around debug
x[1,]  # Needs a space after the comma



### 2.4 Curly Braces
An opening curly brace should never go on its own line; a closing curly brace should always go on its own line. You may omit curly braces when a block consists of a single statement; however, you must consistently either use or not use curly braces for single statement blocks.


if (is.null(ylim)) {
  ylim <- c(0, 0.06)
}
xor (but not both)


if (is.null(ylim))
  ylim <- c(0, 0.06)
Always begin the body of a block on a new line.

BAD:
if (is.null(ylim)) ylim <- c(0, 0.06)
if (is.null(ylim)) {ylim <- c(0, 0.06)}

### 2.5 Surround else with braces
An else statement should always be surrounded on the same line by curly braces.


if (condition) {
  one or more lines
} else {
  one or more lines
}
BAD:

if (condition) {
  one or more lines
}
else {
  one or more lines
}
BAD:

if (condition)
  one line
else
  one line


### 2.6 Assignment
Use <-, not =, for assignment.

GOOD:
x <- 5

BAD:
x = 5

### 2.7 Semicolons
Do not terminate your lines with semicolons or use semicolons to put more than one command on the same line. (Semicolons are not necessary, and are omitted for consistency with other Google style guides.)

### 2.8 Organization
General Layout and Ordering
If everyone uses the same general ordering, we'll be able to read and understand each other's scripts faster and more easily. CMU references provide more details on code Layout and Organization.

### 2.9 Copyright statement comment
Author comment
File description comment, including purpose of program, inputs, and outputs
source() and library() statements
Function definitions
Executed statements, if applicable (e.g., print, plot)
Unit tests should go in a separate file named originalfilename_test.R.

### 2.10 Commenting Guidelines
Comment your code. Entire commented lines should begin with # and one space.

Short comments can be placed after code preceded by two spaces, #, and then one space.
```sh
# Create histogram of frequency of campaigns by pct budget spent.
hist(df$pct.spent,
     breaks = "scott",  # method for choosing number of buckets
     main   = "Histogram: fraction budget spent by campaignid",
     xlab   = "Fraction of budget spent",
     ylab   = "Frequency (count of campaignids)")

```

### 2.11 Function Definitions and Calls
Function definitions should first list arguments without default values, followed by those with default values.

In both function definitions and function calls, multiple arguments per line are allowed; line breaks are only allowed between assignments.
GOOD:

PredictCTR <- function(query, property, num.days,
                       show.plot = TRUE)
BAD:

PredictCTR <- function(query, property, num.days, show.plot =
                       TRUE)
Ideally, unit tests should serve as sample function calls (for shared library routines).

### 2.12 Function Documentation
Functions should contain a comments section immediately below the function definition line. These comments should consist of a one-sentence description of the function; a list of the function's arguments, denoted by Args:, with a description of each (including the data type); and a description of the return value, denoted by Returns:. The comments should be descriptive enough that a caller can use the function without reading any of the function's code.

Example Function
```sh CalculateSampleCovariance <- function(x, y, verbose = TRUE) {
  # Computes the sample covariance between two vectors.
  #
  # Args:
  #   x: One of two vectors whose sample covariance is to be calculated.
  #   y: The other vector. x and y must have the same length, greater than one,
  #      with no missing values.
  #   verbose: If TRUE, prints sample covariance; if not, not. Default is TRUE.
  #
  # Returns:
  #   The sample covariance between x and y.
  n <- length(x)
  # Error handling
  if (n <= 1 || n != length(y)) {
    stop("Arguments x and y have different lengths: ",
         length(x), " and ", length(y), ".")
  }
  if (TRUE %in% is.na(x) || TRUE %in% is.na(y)) {
    stop(" Arguments x and y must not have missing values.")
  }
  covariance <- var(x, y)
  if (verbose)
    cat("Covariance = ", round(covariance, 4), ".\n", sep = "")
  return(covariance)
}

```


### 2.13 TODO Style
Use a consistent style for TODOs throughout your code.
TODO(username): Explicit description of action to be taken

### 2.14 Language
Attach
The possibilities for creating errors when using attach are numerous. Avoid it.

Functions
Errors should be raised using stop().

### 2.15 Objects and Methods
The S language has two object systems, S3 and S4, both of which are available in R. S3 methods are more interactive and flexible, whereas S4 methods are more formal and rigorous. (For an illustration of the two systems, see Thomas Lumley's "Programmer's Niche: A Simple Class, in S3 and S4" in R News 4/1, 2004, pgs. 33 - 36: https://cran.r-project.org/doc/Rnews/Rnews_2004-1.pdf.)

Use S3 objects and methods unless there is a strong reason to use S4 objects or methods. A primary justification for an S4 object would be to use objects directly in C++ code. A primary justification for an S4 generic/method would be to dispatch on two arguments.

Avoid mixing S3 and S4: S4 methods ignore S3 inheritance and vice-versa.

### 2.16 Exceptions
The coding conventions described above should be followed, unless there is good reason to do otherwise. Exceptions include legacy code and modifying third-party code.

Parting Words
Use common sense and BE CONSISTENT.

If you are editing code, take a few minutes to look at the code around you and determine its style. If others use spaces around their if clauses, you should, too. If their comments have little boxes of stars around them, make your comments have little boxes of stars around them, too.

The point of having style guidelines is to have a common vocabulary of coding so people can concentrate on what you are saying, rather than on how you are saying it. We present global style rules here so people know the vocabulary. But local style is also important. If code you add to a file looks drastically different from the existing code around it, the discontinuity will throw readers out of their rhythm when they go to read it. Try to avoid this.




# Python Style Guide
Python is the main dynamic language used at most teams including [LotusX].


[Style Guide for Python Code from Python.org](https://www.python.org/dev/peps/pep-0008/)
[Google Guide for Python Code](https://google.github.io/styleguide/pyguide.html)

### Run Yapf
[Example of a Yapf edit](https://github.com/google/yapf/)
```sh x  

x = {  'a':37,'b':42, 'c':927}

y = 'hello ''world'
z = 'hello '+'world'
a = 'hello {}'.format('world')
class foo  (     object  ):
  def f    (self   ):
    return       37*-+2
  def g(self, x,y=42):
      return y
def f  (   a ) :
  return      37+-+a[42-x :  y**3]
```
reformat it to:

```sh x  

x = {'a': 37, 'b': 42, 'c': 927}
y = 'hello ' 'world'
z = 'hello ' + 'world'
a = 'hello {}'.format('world')


class foo(object):
    def f(self):
        return 37 * -+2

    def g(self, x, y=42):
        return y


def f(a):
    return 37 + -+a[42 - x:y**3]
```



### Lint
Run pylint over your code.

### Imports
Use import for packages and modules only. If you are using Eclipse or an IDE that tends to import classes make necessary changes. Refer to [Google Python Guide for more details on import guidelines](https://github.com/google/styleguide/blob/gh-pages/pyguide.md)

### Exceptions
Allowed at higher function level but for two reasons should be avoided especially if being used at low-level:
* complicates group testing
* harder to read for unit testing

### Global Variables
Python is a dynamic programming language. Variables that are declared at the module level or as class attributes can affect modules and classes during import. Avoid using Global Variables.

### List Comprehension
Use in methods and simple cases only and consistently. If you are using list comprehension to assign Dataframe values to tupples always stick to it in your code across all your methods.  

### Generator Expression
See List Comprehension.

### Default Iterator and Operators
Use them.
```sh Yes
      for key in adict: ...
      if key not in adict: ...
      if obj in alist: ...
      for line in afile: ...
      for k, v in dict.iteritems(): ...

```


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

[LotusX]: <https://lotustech.io>
