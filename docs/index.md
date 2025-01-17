---
title: "An introduction to R for sensory and consumer scientists"
author: 
  - Jacob Lahne^[Virginia Tech, jlahne@vt.edu]
  - Leah Hamilton^[Virginia State University, lhamilton@vsu.edu]
site: "bookdown::bookdown_site"
documentclass: book
output:
  bookdown::gitbook: default
  bookdown::pdf_book: default
github-repo: lhami/pangborn-tutorial-2023
---

# Introduction and welcome {-}




Welcome to the Pangborn Sensometrics Workshop "**An introduction to R for sensory and consumer scientists**"!

This workshop is going to be conducted not using slides, but through **livecoding**.  That means we are going to run code lines in the console or highlight and run code in scripts and other files.  It is also an opportunity and encouragement for you to follow along.  Along with introducing ourselves for today's workshop, we're going to discuss a bit about how that will work here.

## Introductions {-}

### Leah Hamilton, PhD {-}

Leah Hamilton is an Assistant Professor of Sensory & Flavor Science at Virginia State University, in the US. Her primary research interest is flavor language, including the ways that people talk about flavors using their own words in different contexts. In her new position at Virginia State University, she'll be working closely with plant breeders and agricultural scientists to develop sensory-driven specialty crops and support the work of small and underprivileged farmers in the mid-Atlantic US.

### Elizabeth Clark, PhD {-}

Elizabeth Clark is a Senior Scientist in Sensory & Consumer Sciences at McCormick & Company Inc. — a global leader in flavor operating in two segments across 170 countries and territories. McCormick’s passion for Sensory & Consumer Science has led to published research on a replacement for the Scoville heat method for the sensory determination of pungency in capsicum products (Gillette, Appel, & Leggo, 1984); The Sensory Quality System (SQS): a global quality control solution (King et.al, 2022); the EsSense Profile®— a scientific measurement of the human emotional response to flavor (King & Meiselman, 2010), and The Wellsense Profile™ — a questionnaire to measure consumer wellness with foods (King et.al, 2015). Leveraging her interests in data analytics & coding, Elizabeth is helping McCormick usher in a new era of sensory research geared toward addressing rapidly evolving challenges faced by global food & beverage companies.

### Sébastien Lê, PhD {-}

Sébastien Lê is an Associate Professor of Statistics and Computer science at l’Institut Agro Rennes-Angers, in France. He's a co-author of the FactoMineR and SensoMineR R packages, a co-author of [*Analyzing Sensory Data with R*](https://doi.org/10.1201/9781315373416), and a co-author of the Sensory %>% Data %>% Science educational platform.
He's always curious and open to all kind of collaborations.

### Jacob Lahne, PhD {-}

Jacob Lahne is an Associate Professor of Food Science & Technology at Virginia Tech, in the United States.  He runs the Virginia Tech Sensory Evaluation Laboratory, as well as teaching courses in data analytics and coding for food-science research.  His main research focuses are sensory data-analysis methodologies and investigating the sensory properties of fermented and distilled foods and beverages. His work was invaluable in putting this workshop together, but unfortunately he won't be joining us in Nantes.

## Today's agenda {-}

Today's workshop is going to take ~3 hours, with a break for lunch, and we'll be covering the following material:  

1.  Crash course in using R  
2.  Creating, importing, and manipulating data in R
3.  Tidy Data Analysis: Rows, Columns, and Groups
    1. What is tidy data?
    2. Subsetting data
    3. Chaining steps together
    4. Making new variables
    5. Groups of rows and split-apply-combine
    6. Groups of columns
4. Tidy Data Analysis: Reshaping and combining tables
    1. Wider and longer data
    2. Combining data frames
    3. Other data-wrangling utilities
5.  Data analysis outside the `tidyverse`
    1. Correspondence Analysis overview
    2. Working with binary, count, and character data
    3. Untidying & Retidying data
6.  Basics of data visualization in `R`/`ggplot2`
    1. Built-in plots using ca package
    2. Customizing plots with ggplot2
  
## How we're going to run {-}

This workshop is going to be run with **livecoding**, as noted above.  This means we won't be using slides or a prepared video, but running through code step by step to show how these tools are used in practice.  We encourage **you** to also follow along with livecoding, because the best way to learn coding is to actually do it.

### Recommended approach for livecoding {-}

We recommend that you download the pre-made archive of code and data from the [workshop github repo](https://github.com/lhami/pangborn-tutorial-2023).  This archive, when unzipped, will have a folder structure and a `.Rproj` file.  We recommend that you close out RStudio, unzip the archive, and double click the `.Rproj` file *in that folder*, which will open a new session of RStudio with proper setting (like the home directory) for the files for this workshop.

In that folder, you will find a `data/` folder with the necessary data for the workshop, and a script named `pangborn-all-code.R`.  This latter file contains all of the code demonstrated in this workshop for your future reference.  You can also follow along with the code at the [workshop's page hosted on github.io](https://lhami.github.io/pangborn-tutorial-2023) (which you're reading right now), and which will remain available after this workshop.

Once you're in RStudio, go to the `File > New File > R Script` menu to open a new script.  We'll talk about how these work in a minute, but this is basically a workbook for you to store sequential lines of code to be run in the `Console`.  It is where you can livecode along!  Even though we are giving you all of the code you need right now, you will learn a lot more if you actively follow along, rather than just run that code.

### Dealing with errors {-}

Coding means **making mistakes**.  This is fine--as you will surely see today, I will make a ton of trivial errors and have to fix things on the fly.  If you run into trouble, try looking carefully at what you've done and see if you can see what went wrong.  If that fails, we are here to help!  Because we have 3 instructors for this workshop, two of us are available to help at any time.  

When you run into trouble, please use the **red sticky note** by putting it on the back of your laptop.  We'll be keeping an eye out, and someone will come to help you.  When you've resolved your problem, take the sticky note back off.  This way you don't have to raise your hand and interrupt the workshop, etc.  However, if your issue is a common one or something we think is worth noting, don't worry--we'll make time to discuss it!
