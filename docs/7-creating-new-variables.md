---
title: Creating new variables
parent: Cleaning data in STATA
nav_order: 7
layout: default
---

***Creating new variables***

There are two main commands you need to know to generate new variables: “gen” is for the basics, while “egen” allows you to get pretty fancy. You can combine these with qualifiers such as “if” or “in” as well as prefix such as “by” and “bysort” <sup><a href="#note-14" id="ref-14">[14]</a></sup>.

For example, say you want to create a variable that tells you whether the women in the dataset have a live-in partner. While there is no sure-fire way to establish that, we will approximate it by assuming that women who indicated their marital status as married or common-law actually live with their spouse or common-law partner:

![]({{ '/assets/images/22.png' | relative_url }})

The first line creates the variable “livein” and assigns it a value of 1 if the value of the marital status variable (dhhgms) is either 1 (married) or 2 (common-law). The second line replaces the missing value code by 0, making the “livein” variable binary.

Now, let’s say you would like to create a categorical variable that tells you, by age group, if a woman is below or above average in terms of body mass index (BMI).

![]({{ '/assets/images/23.png' | relative_url }})

The first line of command creates a variable (meanbmi) which takes on a unique value for each age group, the average BMI for that age group. The prefix “bysort” is a combination of “by” and “sort”; you could equivalently break it into two commands:

sort DHHGAGE

by DHHGAGE: egen meanbmi=mean(HWTGBMI)

The “sort” part of the command organizes the observation according to the variable DHHGAGE, from smallest to largest, a step required before doing any action “by” the variable. It’s usually easier to just use “bysort”.

The second and third lines (starting with “gen”) create a binary variable which equals 0 if an observation has a BMI lower than the average for her age group, and 1 if her BMI is above her age group average.

---
<p id="note-14"><a href="#ref-14">[14]</a> All of these commands, qualifiers and prefixes have Stata help files. Have a look at them for a more in-depth presentation.
