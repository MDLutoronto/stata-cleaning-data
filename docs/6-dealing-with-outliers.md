---
title: Dealing with outliers
parent: Cleaning data in STATA
nav_order: 6
layout: default
---

***Dealing with outliers***

Outliers deserve their own section because there is often confusion as to what exactly constitutes an outlier. An outlier is NOT an observation with an unusual but possible value for a variable <sup><a href="#note-12" id="ref-12">[12]</a></sup>; rare events do occur. The outliers you should be concerned about are the ones that come from coding error. How do you tell which is which? Common sense goes a long way here.

First, look at your data using the data editor (browse). Outliers tend to jump at you. If you have a small dataset, you can also tabulate each of your variables:

tab *varlist* <sup><a href="#note-13" id="ref-13">[13]</a></sup>

Tabulating a variable will give you a list of all the possible values that variable takes in the dataset. Outliers will be the extreme values. Look at the order of magnitude. Are these values believable?

If the dataset is very big, however, it may not be practical to stare at all the values a variable can take. In fact, Stata will not tabulate if there are too many different values.

You can look at your data in a scatter plot:

![]({{ '/assets/images/18.png' | relative_url }})

In the CCHS dataset, caseid is the individual id, while hwtghtm is the height in meters. The graph tells us there are no outliers in this dataset:

![]({{ '/assets/images/19.png' | relative_url }})

Another way to look for outliers is to summarize the observations for a variable, using the detailed option:

![]({{ '/assets/images/20.png' | relative_url }})

The result window will show the main percentiles of the distribution (including the median – 50%), the first four moments, as well as the four smallest and four largest observations:

![]({{ '/assets/images/21.png' | relative_url }})

Clearly, there are no outliers. Let’s imagine for a moment that the 99 percentile of the height distribution includes an observation with 5.2m entered as the height. Is it plausible that there really was a 5.2m woman recorded in this dataset? Look at the order of magnitude by which this observation would differ from the second largest. It’s almost 50 standard deviations bigger...

What should you do with such an observation? There are a number of solutions but none is perfect:

* Drop it from your dataset (“drop if hwtghtm>1.803”)
* Use the “if” qualifier to exclude it when generating statistics that use the height variable (“*command* if hwtghtm<=1.803”)
* Ignore it if the height variable is not actually that important in your research and the rest of the variables for this observations are coded just fine

---
<p id="note-12"><a href="#ref-12">[12]</a> Admittedly, these are indeed outliers, just not the type we want to do anything about. Leave those alone. “Dealing” with true events in any way is likely to do more harm than good as you would truncate your dataset, potentially creating bias in your analysis later.

<p id="note-13"><a href="#ref-13">[13]</a> You replace “*varlist*” with the list of the variables you want tabulated, as in the drop example.