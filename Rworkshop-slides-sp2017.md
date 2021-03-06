R for Beginners
========================================================
author: Jeho Park
date: Feb 1, 2017
transition: none

HMC Scientific Computing Workshop Series, Spring 2017

https://github.com/jehopark/r-workshop-for-beginners-sp2017.git

Some Housekeeping Stuff
========================================================
- **Slides** at http://bit.ly/hmc-r-workshop-slides-sp2017
- **R files** at http://bit.ly/hmc-r-workshop-github-sp2017
- **Sign-in** at http://bit.ly/hmc-r-workshop-sign-in
- **Digital badge requirements**
  - Attend the workshop (Sign-in above)
  - Your work in RStudio (R file submission)

Workshop Agenda: Real Basics of R
========================================================
* What is R?
* What is not R?
* Then Why R?
* What is RStudio?
* What can you do with it? (some math example)

Workshop Agenda: Basics of R
========================================================
* Demos, search, and help documents
* Workspace of R
* R Objects: Vector, Matrix, List, Data Frame, Factor, Function
* Converting between different types
* Working with Data: Import/Export, subsetting

What is R?
========================================================
* R is a statical programming language/environment.
* R is open source/free.
* R is widely used/prefered.
* R is cross-platform.
* R is hard to learn (really?).

What is not R?
========================================================
* S: R's ancestor
* S-Plus: Commercial; modern implementation of S
* SAS: Commercial; widely used in the commercial analytics.  
* SPSS: Commercial; easy to use; widely used in Social Science.
* MATLAB: Commercial; can do some Stats. 
* Python: Also can do some Stats; good in text data manipulation.

Then Why R?
========================================================
* __R community is active and constantly growing__
* R is one of the most popular stat programming lang
* R has tons of user generated libraries/packages
* R code is easily shared with others
* R is constantly improved

***

![R listserv help](Rworkshop-slides-figure/r-listserv.png)


Then Why R?
========================================================
* R community is active and constantly growing
* __R is one of the most popular stat programming lang__
* R has tons of user generated libraries/packages
* R code is easily shared with others
* R is constantly improving

###### Further reading about R's popularity in science and engineering:<br>
###### R moves up to 5th place in IEEE language rankings at  https://www.r-bloggers.com/r-moves-up-to-5th-place-in-ieee-language-rankings/

***

![R Google Scholar Hit](Rworkshop-slides-figure/Fig_2f_ScholarlyImpactLogs.png)


Then Why R?
========================================================

* R community is active and constantly growing
* R is one of the most popular stat programming lang)
* __R has tons of user generated libraries/packages__
* R code is easily shared with others
* R is constantly improved


***

![R Extentions](Rworkshop-slides-figure/r-extensions.png)

Getting help online and offline
===============================
* Rseek meta search engine: http://rseek.org/ 
* R-help listserv: https://www.r-project.org/mail.html
* Stack Overflow: http://stackoverflow.com/questions/tagged/r
* Cross-Validated: the statistics Q&A site http://stats.stackexchange.com/
* Contact CIS: helpdesk@hmc.edu or jepark@hmc.edu
* HMC R Users Group: r-users-l@g.hmc.edu

Some R Vocabulary
========================================================
* **packages** are add on features to R that include data, new functions and methods, and extended capabilities. Think of them as ``apps'' on your phone. We've already installed several!
* **console** is the main window of R where you enter commands
* **scripts** are where you store commands to be run in the terminal later, like syntax files in SPSS or .do files in Stata
* **functions** are commands that do something to an object in R
* **workspace** is the working memory of R where all objects are stored
* **vector** is the basic unit of data in R
* **dataframe** is the main element for statistical purposes, an object with rows and columns that includes numbers, factors, and other data types

What is RStudio?
========================================================
* Integrated Development Environment for R
* Nice combination of GUI and CLI
* Free and commercial version
* 4 main windows, tabs, etc
* Version control: Git and VPN
* R Markdown
* R Presentation

Get ready
========================================================
* Open RStudio!

What Can We Do with RStudio?
========================================================

![RStudio](Rworkshop-slides-figure/rstudio_image.png)


Look Ma, R can do Math! 
========================================================

```r
1+1
```


```r
2+runif(1,0,1)
```


```r
2+runif(1,min=0,max=1)
```


```r
3^2
```


```r
3*3
```


```r
sqrt(3*3) # comments
```


```r
# comments are preceded by hash sign
```

Even More Math! 
========================================================
* R can take integrals and derivatives, for example:

Numerical Integral of

$\displaystyle\int_0^{\infty} \frac{1}{(x+1)\sqrt{x}}dx$ 


```r
integrand <- function(x) {1/((x+1)*sqrt(x))} ## define the function
```

```r
integrate(integrand, lower=0, upper=Inf) ## integrate the function from 0 to infinity
```

```
3.141593 with absolute error < 2.7e-05
```

Some General Stuff
========================================================

```r
demo() # display available demos
```

```r
demo(graphics) # try graphics demo
```

```r
library() # show available packages on the computer
```

```r
search() # show loaded packages
```

```r
?hist # search for the usage of hist function
```


```r
??histogram # search for package documents containing the word "histogram"
```

Workspace of R
========================================================

R workspace stores objects like vecors, datasets and functions in memory (the available space for calculation is limited to the size of the RAM).


```r
a <- 5 # notice a in your Environment window
```


```r
A <- "text" 
```


```r
a
A
ls()
print(c(a,A))
print(a,A)
```

R as a Programming Language: R Objects
========================================================
__VECTOR__ (homogeneous) <br>
A vector is an array object of the same type data elements.


```r
class(a)
```

```r
class(A)
```

```r
B <- c(a,A) # concatenation
```

```r
print(B)
```

```r
class(B) # why?
```

R Objects: Vectors (cont.)
========================================================
R has five basic or “atomic” classes of objects: 
* character
* numeric (real numbers) 
* integer
* complex
* logical (True/False)

A vector contains a set of data in any one of the atomic classes.


R as a Programming Language: R Objects
========================================================
__Matrices__ (homogeneous) <br>
A matrix is a two-dimensional rectangular object of the __same type__ (homogeneous) data elements. 


```r
mat <- matrix(rnorm(6), nrow = 3, ncol = 2) 
mat # a matrix
dim(mat) # dimension
t(mat) 
summary(mat) 
```

R as a Programming Language: R Objects
========================================================
__LIST__ (heterogeneous)<br>
A list is an object that can store different types of vectors. 

```r
aList <- list(name=c("Joseph"), married=T, kids=2)
aList
aList$kids <- aList$kids+1
aList$kids
aList2 <- list(numeric_data=a,character_data=A)
aList2
allList <- list(aList, aList2)
allList # a list of lists
```

R as a Programming Language: R Objects
========================================================
__Data Frame__ (heterogeneous and homogeneous)<br>
A data frame is used for storing data tables. It is a list of vectors of equal length. 

```r
n <- c(2, 3, 5) # a vector 
s <- c("aa", "bb", "cc") # a vector
b <- c(TRUE, FALSE, TRUE) # a vector
df <- data.frame(n, s, b) # a data frame
df
mtcars # a built-in (attached) data frame
mtcars$mpg
```

R as a Programming Language: R Objects
========================================================
__Data Frame__ (cont.)<br>

```r
myFrame <- data.frame(y1=rnorm(100),y2=rnorm(100), y3=rnorm(100))
head(myFrame) # display first few lines of data
names(myFrame) # display column names
summary(myFrame) # output depends on the data types
plot(myFrame)
myFrame2 <- read.table(file="http://scicomp.hmc.edu/data/R/Rtest.txt", header=T, sep=",")
myFrame2
```

R as a Programming Language: R Objects
========================================================
__FACTOR__
* Factors are a special compoud object used to represent categorical data such as gender, social class, etc.
* Factors have 'levels' attribute. They may be nominal or ordered.

```r
v <- c("a","b","c","c","b")
x <- factor(v) # turn the character vector into a factor object
z <- factor(v, ordered = TRUE) # ordered factor
x
z
table(x)
```

R as a Programming Language: R Objects
========================================================
__Function__ <br>
Functions are also objects in R environment

```r
fun <- function(a,b) {
  a*b
}

fun   
fun(2,3) # a function call
```

Converting between different types
==============================================
Use of the as() family of functions. Type as. and wait to see the list of as() functions.

```r
integers <- 1:10
as.character(integers)
as.numeric(c('3.7', '4.8'))
```

```r
indices <- c(1.7, 2.3)
integers[indices] # sometimes R is too generous
integers[0.999999999] # close to 1 but...
```

```r
df <- as.data.frame(mat)
df
```

Working with Data
=============================
* Working with raw data (text files)
* Data import and export
* Subsetting
* Using data frames vs. matrices

Working with Raw Data (text files)
==============================
* Use read.table() to read text files into R
* Try help document for read.table()

Data Import
==============================
* read.csv() is a special case of read.table() 
* Data import from your local folder

```r
cpds <- read.csv(file.path('.', 'data', 'cpds.csv'))
head(cpds) # good to look at a few lines
class(cpds) # data.frame
```
* Data import from the Internet

```r
data <- read.table(file="http://scicomp.hmc.edu/data/R/normtemp.txt", header=T)
tail(data)
```

Data Import (Cont.)
================================

```r
rta <- read.table("./data/RTADataSub.csv", sep = ",", head = TRUE)
dim(rta)
rta[1:5, 1:5]
class(rta)
class(rta$time) # what? let's see ?read.table more carefully
```

```r
rta2 <- read.table("./data/RTADataSub.csv", sep = ",", head = TRUE, stringsAsFactors = FALSE)
class(rta2$time)
```

Data Export
=============================
* Use write.table() to write data to a CSV file

```r
write.csv(data, file = "temp.csv", row.names = FALSE) 
```
* Save all the objects in current environmet 

```r
save.image(file="myenv.RData") 
# Q: How to load them back later?
```

Subsseting
=========================
Operators that can be used to extract subsets of R objects.
* '[' and ']' always returns an object of the same class as the original; can be used to select more than one element.
* '[[' and ']]' is used to extract elements of a list or a data frame; it can only be used to extract a single element.
* $ is used to extract elements of a list or data frame by name.

Subsetting (cont.)
==========================

```r
x <- c("a", "b", "c", "c", "d", "a")
x[1]
x[1:4]
x[x > "a"] 
u <- x > "a" # what's u here?
u
x[u] # subsetting using a boolean vector
y <- list(foo=x, bar=x[u]) 
y
y[[1]]
y$bar
```

```r
subset(mtcars, gear == 5) # use of subset function for data frames
```

Data frame vs matrix
================================
Consider the following:
* Same types or different types? Numeric or other type?
* Convenient using $ with col names?
* Data size too big? (memory efficiency and size)

```r
m = matrix(1:400000, 2, 200000) # esp. for a large number of columns!
d = as.data.frame(m)
object.size(m) # 1600200 bytes
object.size(d) # 22400568 bytes
```
* Conversion between data frame and matrix
  + as.data.frame()
  + as.matrix() or data.matrix() # consider coercion
  

That's it!
========================================================

Please submit your R environemnt file* at http://bit.ly/hmc-r-workshop-sign-in (digital badge requirement).

*You should know how to export the objetcs in your environment to a Rdata file.

__Further Study!__

* Online learning resources: https://www.rstudio.com/online-learning/#R
* Swirl (self-paced interactive learning) package: http://swirlstats.com/ 


