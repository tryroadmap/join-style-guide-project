# style-guide
Exercise the style guides here. Someone other than you will be reviewing your work. Style guides are coding etiquette.

- [R Style Guide](#r-style-guide)
- [Python Style Guide](#python-style-guide)

This is from Google's R Style Guide and CMU (names, alignment, locality, and comments) coding guidelines. For more details visit:
- [Google R Style Guide](https://google.github.io/styleguide/Rguide.xml)
- [CMU Code Style](https://www.cs.cmu.edu/~pattis/15-1XX/15-200/lectures/style/lecture.html)
- [CMU Code Style](http://www.cs.cmu.edu/~./213/codeStyle.html)




# R Style Guide
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

## Notation and Naming

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
## Syntax
### 2.1 Line Length
The maximum line length is 80 characters.

### 2.2 Indentation
When indenting your code, use two spaces. Never use tabs or mix tabs and spaces.
Exception: When a line break occurs inside parentheses, align the wrapped line with the first character inside the parenthesis.



# Python Style Guide
coming soon.

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

[LotusX]: <https://lotustech.io>
