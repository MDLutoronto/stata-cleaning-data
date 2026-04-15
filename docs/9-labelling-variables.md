---
title: Labelling variables
parent: Cleaning data in STATA
nav_order: 9
layout: default
---

***Labelling variables***

Whenever you create a new variable, it is a good idea to label it. Why? Having your variables labeled makes it easy for you or anyone else using your dataset to quickly see what each variable represents. You should think of your work as something that people should be able to reproduce. Labeling your variables is a small task that makes it much easier for others to use your data <sup><a href="#note-15" id="ref-15">[15]</a></sup>.

The syntax for labeling variables is as follow:

label variable *varname* “*label*”.

In our previous example, the command would look like this:

![]({{ '/assets/images/28.jpg' | relative_url }})

Note that you can abbreviate this command to lab var:

![]({{ '/assets/images/29.png' | relative_url }})

---
<p id="note-15"><a href="#ref-15">[15]</a> Knowing how to label variables can also be useful if the data was not provided to you with a dictionary file; you can then use the questionnaire to build labels for all your variables of interest, just as a dictionary file would do.  
</p>