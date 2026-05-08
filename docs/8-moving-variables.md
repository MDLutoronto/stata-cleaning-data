---
title: Moving variables
parent: Cleaning data in STATA
nav_order: 8
layout: default
---

***Moving variables***

Now that you have created these new variables, it would be nice to make sure that the rules by which you generated them was correct. Ideally, you would like to look at livein (the new variable based on marital status) and dhhgms (the marital status variable). However, it’s hard to compare two variables unless they are side by side. You can use the “order” command to move a variable (i.e. move a column of your dataset).

When you create a variable, by default it becomes the last column of your dataset. You can move it next to another variable instead:

![]({{ '/assets/images/24.png' | relative_url }})

Now if we look at our dataset, we can see compare the new variable to the old and make sure that we coded it properly:

![]({{ '/assets/images/25.png' | relative_url }})

Similarly, since our two new variables pertaining to BMI are now the last columns, let’s move the original BMI variable to the end of the dataset:

![]({{ '/assets/images/26.png' | relative_url }})

It now easy to glance at our new variables:

![]({{ '/assets/images/27.png' | relative_url }})

Do you notice the problem on line 8? The variable bmicat should not be coded 1 if the original BMI variable is coded as a missing value. We can fix this with a quick replace:

replace bmicat=. if hwtgbmi==.d