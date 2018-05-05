# RGPR tutorial - Getting started
Emanuel Huber (emanuel.huber@alumni.ethz.ch)  
`r format(Sys.Date(), "%d %B %Y")`  



***

`RGPR` is a package for [R](https://cran.r-project.org/) to read, write, analyse and visualise ground-penetrating radar (GPR) data.
  

**Note**: 

* This R-package is still in development, and therefore some of the functions may change in a near future. 
* The R-package `RGPR` is hosted on [GitHub](https://github.com/) at [https://github.com/emanuelhuber/RGPR](https://github.com/emanuelhuber/RGPR). 
* You can contribute to the development of `RGPR`: 
    1. create an account on [GitHub](https://github.com/),
    2. [fork](https://guides.github.com/activities/forking/) `RGPR`, 
    3. change the code
    4. make a [pull request](https://guides.github.com/activities/forking/#making-a-pull-request) (sumbmit your modifications).

If you have any questions, comments or wishes, etc. feel free to contact me (in english, french or german): <emanuel.huber@alumni.ethz.ch>.

# Objectives of this tutorial

* Learn how to install the R-package `RGPR`.
* Learn how to load the R-package `RGPR` in your current R session.

<!--
In this tutorial the code snippets are in monospaced typewriter font like in the following example:

```r
1 + exp(1:10)
```

The R output are preceded by a double hash (`##`). The following R output is from the code snippet above.

```
##  [1]     3.718282     8.389056    21.085537    55.598150   149.413159
##  [6]   404.428793  1097.633158  2981.957987  8104.083928 22027.465795
```

Create a text file and save it with the `.R` extension (the extension for the R-script files). Then copy the code snippets into your R-script file and adapt them to your needs. To run the code in R, copy the code and paste it into the R console. You can also manually enter the code.

Don't hesitate to consult the help files and to search for help on the internet. For example, to see the help for the function `mean()`, enter:


```r
?mean    # open the help file related to the function mean()
```
--> 

# Software
1. Download R from the [R Cran website](http://cran.r-project.org) and install it.
2. Optionally install a R-GUI:
    * [Notepad++](https://notepad-plus-plus.org/) combined with [NppToR](https://sourceforge.net/projects/npptor/)
    * [Rstudio](https://www.rstudio.com/)
    * [RKward](https://rkward.kde.org/)
3. If necessary, learn some R basics:
    * [An interactive introduction to R](http://tryr.codeschool.com)
    * [Short R introduction](http://cran.r-project.org/doc/contrib/Torfs+Brauer-Short-R-Intro.pdf) 
    * [R course](http://www.rochester.edu/college/psc/thestarlab/help/rcourse/R-Course.pdf)
  
If you are a R-beginner I recommand you to start with [Rstudio](https://www.rstudio.com/) that provides a nice interface for R. With Windows, I prefer to work with [Notepad++](https://notepad-plus-plus.org/) (the best text editor I know) combined with [NppToR](https://sourceforge.net/projects/npptor/). With Linux, I work with [RKward](https://rkward.kde.org/) (because [Notepad++](https://notepad-plus-plus.org/) is not available for linux).
  
# How to install `RGPR`
Start R in the terminal (by entering `R`) or through a R GUI.

The R-package `RGPR` is hosted on GitHub at [https://github.com/emanuelhuber/RGPR](https://github.com/emanuelhuber/RGPR)

Use the function `install_github()` from the R-package `devtools` to install `RGPR` directly from the GitHub repository. But first you need to install and load `devtools`. You can install this package through the GUI (RStudio or RKward) or direclty in R by entering:


```r
install.packages("devtools")     # install "devtools"
```

Select your prefered CRAN mirror and let R install `"devtools"`.

Note: if necessary, use the `lib` argument of the function `install.packages()` to define the library directory where to install the package. 
For example with Ubuntu: `install.packages("devtools", lib="/usr/lib/R/library/")`.

Once the package is installed, you need to load it into the current R session with the `library()` function:


```r
library("devtools")     # load "devtools" into the current R session
```

Now, install `RGPR` from GitHub:

```r
devtools::install_github("emanuelhuber/RGPR")  # install RGPR
```
Note: if necessary, use the `lib` argument of the function `install_github()` to define the library directory where to install the package. 
For example with Ubuntu: `devtools::install_github("username/packagename", lib="/usr/lib/R/library/")`.

# How to load `RGPR`
The installation of `RGPR` has to be done only once. But each time you start a R session and want to use `RGPR`, you must first load it by entering


```r
library(RGPR)   # load RGPR in the current R session
```

**But I recommand you to always re-install `RGPR` because this package is still in development**

# R code

Here is the complete code listing:

```r
install.packages("devtools")     # install "devtools"
library("devtools")              # load "devtools" into the current R session
devtools::install_github("emanuelhuber/RGPR")  # install RGPR
library(RGPR)                    # load RGPR in the current R session
```
<!--
# Suggested file organisation
```
/name_of_survey   (put your R-script)
    /maps         (maps, sketches of the GPR survey)
    /processing   (the processed files)
    /rawGPR       (the raw data, never modify these files)
    /topo         (topographic data)
        /GPS            (GPS data, converted in shapefiles)
        /totalStation   (topographic data measured with a total station)
        /elevationGPR   (if available, 1 file for each GPR file containing
                         the x,y,z coordinates of every traces)
```
-->