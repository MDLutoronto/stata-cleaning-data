---
title: Transforming variables
parent: Cleaning data in STATA
nav_order: 5
layout: default
---

***Transforming variables***

Sometimes variables are not coded the way you want them to be. In this section we will look at two transformations you may need to do on some variables before using them: recode and destring.

The “recode” command changes the values of numeric variables according to the rules specified. In the CCHS dataset, many variables have missing values coded as “.a” or “.d”. This is convenient because it will not affect calculations you might do using the data (for example if you calculate an average). However, many datasets use 999 as a missing variable code, and that might be problematic. We might want to recode these as “.” in order to not have them affect any calculations we plan on doing with the data. The syntax for this command is:

recode *varlist* (old value(s)=new value) <sup><a href="#note-11" id="ref-11">[11]</a></sup>

Let’s recode the height and BMI variables from the CCHS data, (for the sake of illustration, since it’s really not necessary in this case):

![]({{ '/assets/images/13.jpg' | relative_url }})

The “destring” command allows you to convert data saved in the string format (i.e. alphanumeric) into a numerical format. The CCHS dataset does not contain any string variable. In order to see what a string variable looks like, we can use the converse command, “tostring”, to create a string variable. We will then convert that variable back to a numerical format.

![]({{ '/assets/images/14.png' | relative_url }})

A string variable shows up in red in the data editor:

![]({{ '/assets/images/15.png' | relative_url }})

Although it may look the same as the variable CIH_2, Stata cannot do any calculations on the string variable (since its format is telling Stata that it is made of letters or other symbols). Let’s destring it:

![]({{ '/assets/images/16.png' | relative_url }})

Notice the use of the options “generate” and “replace”. When we created the fake string variable, we used “generate” because we wanted a new separate variable. Now, when we destring, we are replacing the string variable by its numerical counterpart. How you choose to do this in your own dataset depends on how you plan to use the variables. Will you still have any use for the string variable? If so generate a new one when you destring. Do you just want that variable to not be in string format? Then replace it with the new one.

Here, we can see that our variable string is now completely identical to the variable CIH_2:

![]({{ '/assets/images/17.png' | relative_url }})

(We can drop that variable now)

---
<p id="note-11"><a href="#ref-11">[11]</a> Note that you can also use this command to make groups. The CCHS dataset already has age by age group but if you had a variable for actual age, you could generate an age group variable using recode. See the Stata help sheet (help recode) for more options.