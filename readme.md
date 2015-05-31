# About 

Insipred by [Princeton DSS's Getting Started in R~Stata](http://dss.princeton.edu/training/RStata.pdf) and [UCLA IDRE's Data Analysis Examples](http://www.ats.ucla.edu/stat/dae/), this document presents Stata commands/functions/user-written commands and R commands/functions/packages in a same table, side by side. The purpose of the document is to ease the transition from a Stata user/developer to an R user/developer. I will try to add one table every day.

# Contributing

Feel free to contribute to the document through a pull request or issue. 
Any improvement, such as fixing typos, reorganizing document struture, or adding new content, is more than welcome.
Below are a few recommendations regarding editing.

- When there are multiple ways of achieveing a same result, we can offer a small note under the table.
- We don't mind putting up Stata commands that are only available in the newest version, but again, we can offer a small note.
- When we have options from base R and [the Hadleyverse](http://blog.revolutionanalytics.com/2015/03/hadleyverse.html), we opt for tools available in the Hadleyverse.  

# Table of Contents

- [Miscellaneous](#misccellaneous)
    - [Getting Help](#getting-help)
    - [Navigate Directories](#navigate-directories)
    - [Comment](#comment)
    - [Installing Packages](#installing-packages)
- [Ingest Data](#ingest-data)
    - [Import and Export Delimited Data](#import-and-export-delimited-data)
    - [Import and Export Stata `dta` File](#import-and-export-stata-dta-file)

# Miscellaneous

## Getting Help

| Tasks                           | Stata           | R            |
| :-----------------------------  | ---------------:| ------------:|
| Get the help document           | `help` or `man` | `?`          |
| Search for keywords             | `search`        | `??`         |

[Back to TOC ⤣](#table-of-contents)

## Navigate Directories

| Tasks                           | Stata           | R            |
| :-----------------------------  | ---------------:| ------------:|
| Show working directory          | `pwd`           | `getwd()`    |
| Set working directory           | `cd`            | `setwd()`    |
| list files in working directory | `ls`            | `list.file()`| 

[Back to TOC ⤣](#table-of-contents)

## Comment

| Task                            | Stata           | R            |
| :------------------------------ | ---------------:| ------------:|
| Comment out a line              | `*` or `\\`     | `#`          |
| Comment out a block             | `\*` and `*/`   |              |

_Notes:_ 
- If you use R Studio, a keyboard shortcut for comment out a block of code is `Ctrl+Shift+C` for Windows and Linux, and	`Command+Shift+C` for Mac. 

[Back to TOC ⤣](#table-of-contents)

## Installing Packages

| Task                            | Stata           | R                                    |
| :------------------------------ | ---------------:| ------------------------------------:|
| Install and load a package      | `ssc install`   | `install.package()` and `library()`  |

_Notes:_
- The Stata `ssc` command only installs packages that are avaiable from the Boston College Statistical Software Components (SSC) archive, provided by [RePEc](https://ideas.repec.org/s/boc/bocode.html).
- The R function `install.package()` mainly downloads package from the Comprehensive R Archive Network (CRAN).
- Many R package hosted in Github or Bitbucket can be downloaded through functions in the [`devtools` package](https://github.com/hadley/devtools), another star in the Hadleyverse. For example, to install the [package `readr`](https://github.com/hadley/readr) from Github: 
```r
# install.packages("devtools")
devtools::install_github("hadley/readr")
```
[Back to TOC ⤣](#table-of-contents)

# Ingest Data

## Import and Export Delimited Data

| Task                            | Stata                                    | R                                    |
| :------------------------------ | ----------------------------------------:| ------------------------------------:|
| Import CSV Data                 | `import delimited using, delimiter(,)`   | `readr::read_csv()`                  |
| Export CSV Data                 | `export delimited using, delimiter(,)`   | `readr::write_csv()`                 |

[Back to TOC ⤣](#table-of-contents)

## Import and Export Stata dta File

| Task                            | Stata                                    | R                                    |
| :------------------------------ | ----------------------------------------:| ------------------------------------:|
| Import dta Data                 | `use`                                    | `readr::read_dta()`                  |
| Export dta Data                 | `save`                                   | `readr::write_dta()`                 |

_Notes:_
- A base R function for reading csv file is `read.csv()`, which is a wrapper function for `read.table()`.

[Back to TOC ⤣](#table-of-contents)
