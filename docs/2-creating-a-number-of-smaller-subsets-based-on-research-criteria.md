---
title: Creating a number of smaller subsets based on research criteria
parent: Cleaning data in STATA
nav_order: 2
layout: default
---

***Creating a number of smaller subsets based on research criteria***

There are many reasons why you may want a smaller subset of your data but the main one is that the bigger the dataset, the harder it is for Stata to manage, which slows down your system. Your goal is to make your dataset as small as possible, while keeping all the relevant information. Your research agenda determines what your final dataset will contain.
bundle
Let’s say you have data on the health habits of Canadians aged 12 and up, but your research question is specific to women of reproductive age living in Ontario <sup><a href="#note-8" id="ref-8">[8]</a></sup>. You clearly don’t need to keep the men in your dataset, and you won’t need to keep the residents of provinces other than Ontario. Furthermore, you can probably drop women under 15 and over 55 years old. Now, let’s look at how you would do that.

---
<p id="note-8"><a href="#ref-8">[8]</a> The examples in this guide were created using a customized subset of the Canadian community health survey (CCHS), annual component, 2007-2008, available through the Data Liberation Initiative (DLI) and downloaded using [SDA@CHASS](mailto:SDA@CHASS).
