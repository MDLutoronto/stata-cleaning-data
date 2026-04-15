---
title: Dropping observations
parent: Cleaning data in STATA
nav_order: 3
layout: default
---

***Dropping observations***

To drop observations, you need to combine one of two Stata commands (keep or drop) with the “if” qualifier.

Make sure you have saved your original dataset before you get started.

The “keep” command should be used with caution (or avoided altogether) because it will drop all but what you specifically keep. This can be a problem if you are not 100% certain of what you want to keep.

The “drop” command will drop from your dataset what you specifically ask Stata to drop.

The “if” qualifier restricts the scope of the command to those observations for which the value of an expression is true. The syntax for using this qualifier is quite simple:

*command* if *exp*

Where *command* in this case would be, drop and *exp* is the expression that needs to be true for the “drop” command to apply <sup><a href="#note-9" id="ref-9">[9]</a></sup>.

![]({{ '/assets/images/09.png' | relative_url }})

Using the example of women of reproductive age in Ontario, the first highlighted line drops men, the second line drops any observation not in Ontario, while the last line drops observations in age groups older or younger than our subset of interest.

You have to be careful with logical operators; notice the syntax in the third line. A common mistake is to ask Stata to “drop if DHHGAGE>10**&**DHHGAGE<2”. There are no individuals in the dataset who are older than 55 AND younger than 15. We want to drop if older than 55 OR younger than 15.

Here is a list of operators in expressions. You would mostly use logical and relational operators in conjunction with “if”:

![]({{ '/assets/images/10.png' | relative_url }})

---
<p id="note-9"><a href="#ref-9">[9]</a> See the Stata help files on expressions and operators: type “help exp” and “help operator” in the command screen.
