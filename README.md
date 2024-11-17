java c
ECON4003
INTRODUCTION TO STATA
WEEK 3
1  Introduction
1.1    Materials and setup
●    Find class materials on Moodle page
●    Download the folder for Stata session and unzip it!
1.2  Organisation
●    Make comments in your Do-file rather than on self-printed hand-outs
●     save on flash drive or email to yourself
1.3    Lab description
●    This is an introduction to Stata
●    Assumes no/very little knowledge of Stata
●    Learning objectives:
o  Familiarise yourself with the Stata interface
o  Get data in and out of Stata
o  Compute statistics and construct graphical displays
o  Compute new variables and transformations
1.4    What is Stata? Statistics and Data Analysis
●   A statistical package that includes a wide variety of capabilities
o Data management
o Statistical and econometric analysis
o Graphics etc.
●   Widely used in the fields of economics, finance, political science, sociology, biomedicine and epidemiology
●   Three main versions
o Stata/IC (Intercooled): mid-sized datasets
o Stata/SE (Special Edition ): large datasets
o Stata/MP (Multi-processor ): fastest version (for quad-core, dual-core, and multicore/multiprocessor computers)
1.5    Where you can download Stata?
●   See Stata Installation Guide under Course Resources > Resources for Stata
●   Contact IT Helpdesk for any technical issues
1.6    Stata interface

●     Command window:
o Type the instructions we want Stata to execute
o Alternatively, type in the Do-file (see next section)
●     Results window
o Display the results and output after a command is executed
●     Review window
o Keeps arecord of all the commands used/the input history
●    Variables window
o Shows all the variables in the dataset
●     Properties window
o Indicates the properties of a highlighted variable or save any files
●    Current working directory
o Shows the current directory in the file system of your computer from where Stata will read or save any files
1.7    Do-files
●    You can type all the same commands into the Do-file that you would type into the command window
●     BUT...the Do-file allows you to save your commands
●    Saving commands in Do-file allows you to keep a written record of everything you have done to your data
o  Allows easy replication
o  Allows you to go back andre-run commands, analyses and make modifications
1.8    Stata menu
●    An alternative way to tell Stata what you would like it to do is to use menus and dialogs.
●     Stata’s Data, Graphics, and Statistics menus provide point-and-click access to almost every command in Stata.
1.9    Stata help
●    To get help in Stata type “help” followed by topic or command, e.g., help codebook
1.10  General Stata command syntax
●    Most Stata commands follow the same basic syntax:
command varlist, option
1.11  Hand calculator
●     Stata can be used as a calculator using the command: display
display 4+5
dis  3^5
dis  10/5
1.12  Commenting
●    Any command in Stata that is preceded by a star character (*) will be regarded as comment, and therefore, not executed
*This is a comment
2  Getting data into Stata
2.1  Data file commands
●    First, we set the working directory to the folder you saved your data by selecting:
File > Change working directory …
●    Next, we want to open our data file
●    Open/save data sets with "use" and "save"
use “nlsw88small.dta”, clear
save “nlsw88lab1.dta”, replace
The US National Longitudinal Study of Young Women 1998 extract, nlsw88small.dta, contains data of
500 women in their 30s and early 40s to study their labourforce patterns.
2.2 Variable list
Variable                                       代 写ECON4003 INTRODUCTION TO STATAProcessing
代做程序编程语言                     Description
idcode
NLS id
age
age at current year
race
race
married
=1 if married; 0 otherwise
never_married
=1 if never married; 0 otherwise
grade
current grade completed, numerical
collgrad
=1 if college graduate; 0 otherwise
south
=1 if lives in south; 0 otherwise
smsa
=1 if lives in SMSA; 0 otherwise
c_city
=1 if lives in central city; 0 otherwise
industry
industry category
occuptation
occupational category
union
=1 if union worker; 0 otherwise
wage
hourly wage
hours
usual hours worked
ttl_exp
total work experience (years)
tenure
job tenure (years)
3  Statistics and graphs
3.1  Operators
3.1.1 Relational operators
●    >          // greater than
●    <          // less than
●    >=       // greater than or equal
●    <=       // less than or equal
●    ==       // equal
●    !=        // not equal
3.1.2 Logical operators
●             // and
●     |          // or
●     !           // not
3.2  Frequently used commands for reviewing and inspecting data
●     describe          // labels, storage type etc.
describe
des wage age
Exercise: produce a summary describing the variables “union” and “tenure”
●     codebook       // storage type, unique values, labels
codebook wage
Exercise: produce a codebook for the variables “tenure” and “hours”
●    sum                 // statistical summary (mean, sd, min/max etc.)
sum wage
sum wage, detail
sum wage if married==1
sum wage if age>=40  age<=44
Exercise 1: compute the summary statistics for the variable “tenure”
Exercise 2: compute summary statistics for the variable “hours” for individuals aged 40 or 44
●    tab                   // (cross) tabulate frequency counts
tab industry
tab industry, nolabel
tab industry race
Exercise 1: produces a table of frequency counts for the variable “occupation”
Exercise 2: produce a two-way table of frequency counts for the variable “occupation” and “collgrad”
●    browse            // view the data in a spreadsheet-like window
browse
browse wage age
3.3 Basic graphing commands
●    graph pie / bar / hbar          // present categorical data
●     save graphs as jpeg format
graph pie, over(industry)
graph bar, over(race)
graph hbar, over(occupation)
Exercise 1: draw pie chart for “occupation”
Exercise 2: create a bar graph for the variable “married”
Exercise 3: create a horizonal bar graph for the variable “industry”
●    hist                  // univariate distribution(s)
hist wage
hist wage, percent
hist wage, freq
hist wage, normal
Repeat the exercise above for the variable “hours”
●    twoway scatter          // view bivariate distributions with scatterplots
twoway scatter wage tenure
twoway scatter wage tenure, by(race)
Exercise 1: create a scatter plot of “wage” on “ttl_exp”
Exercise 2: create a scatter plots of “wage” on “ttl_exp” by “married”
4  Basic data management
4.1  Generating and replacing variables
●    gen                  // create new variables
gen age2 = age^2
gen lnwage = ln(wage)
Exercise: create a new variable “totwage” which is “wage” multiplied by “hours”
●    replace            // replace variables with new values
replace age2 = age2/100
Exercise: replace “totwage” with the natural log of “totwage”
4.2  Renaming and deleting variables
●    rename            // change variable names
rename age2 agesq
Exercise: rename the variable “totwage” as “lntotwage”
●    drop                // delete variables
drop agesq lnwage
Exercise: drop “totwage”
Save the data and your do-file before you quit the session.


         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
