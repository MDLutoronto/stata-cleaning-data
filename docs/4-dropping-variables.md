---
title: Dropping variables
parent: Cleaning data in STATA
nav_order: 4
layout: default
---

***Dropping variables***

Another way in which you may need to make your dataset smaller is by dropping variables that are not useful to your research. It may be that the information contained in a given variable is duplicated (i.e. another variable provides the same info), or maybe all the observations for a variable are missing, or a variable just happens to be in your dataset but is irrelevant to your research. Dropping variables is very straightforward; simply use the “drop” command.

Looking at the data from CCHS, the variable SLP_01 (Number of hours spent sleeping per night) is coded as “.a” (NOT APPLICABLE) for each observation in the dataset.

![]({{ '/assets/images/11.png' | relative_url }})

Clearly we will not learn anything from that variable, so we can drop it. The syntax for dropping variable is simple:

drop *varlist*

Where *varlist* is the list of variables you would like to drop. It’s easy to drop a number of a variable at a time this way. Here I am dropping all the variables that were coded as Not Applicable for more than 95% of observations <sup><a href="#note-10" id="ref-10">[10]</a></sup>:

![]({{ '/assets/images/12.jpg' | relative_url }})

---
<p id="note-10"><a href="#ref-10">[10]</a> There is no rule of thumb at play here; I simply picked a list of variables that contained little useful information. Sometimes, the fact that only a small number of observations contain information IS informative, in and of itself. Do not drop variables that tell you something important.