---
title: Renaming variables
parent: Cleaning data in STATA
nav_order: 10
layout: default
---

***Renaming variables***

You may find that you work faster if your variables have names that you recognize at first glance. In most cases this is by no means a necessary task in cleaning data, but if you use data from another country, for example, you may find that the variable names are in a foreign language, making it very hard to remember. The syntax is as easy as can be:

rename *oldname* *newname*

![]({{ '/assets/images/30.png' | relative_url }})

Let’s see the final do-file

Your do-file may be slightly different from this but it should result in the same final dataset:

![]({{ '/assets/images/31.png' | relative_url }})

Let’s try running it in one go to see if it works. Do not highlight any command and click on Execute (Do). Note that whenever Stata encounters the command “browse” a data editor will pop up on your screen. Have a look at your data then close the data editor in order for Stata to continue running the do-file.

Let’s also take the time to open our logs to see what it looks like and how it could be useful.

Finally let’s look at our final datasets and make sure it contains all the right variables, in the right format.