---
title: Some useful tips before you get started
parent: Cleaning data in STATA
nav_order: 1
layout: default
---



***Some useful tips before you get started*** <sup><a href="#note-1" id="ref-1">[1]</a></sup>


*Use the Stata help file*. Stata has a built in feature that allows you to access the user manual as well as help files on any given command. Simply type “help” in the command window, followed by the name of the command you need help with and press the Enter key:

![]({{ '/assets/images/01.png' | relative_url }})

*Write a do file.* Never clean a dataset by blindly entering commands (or worse, clicking buttons). You want to write the commands in a do-file, and then run it. This way, if you make a mistake, you will not have ruined your entire dataset and you will not need to start again from scratch. This is a general advice that applies to any work you do on Stata. Working from do-files lets other people see what you did if you ever need advice, it makes your work reproducible and it allows you to correct small mistakes somewhat painlessly.

To start a do-file, click on the icon that looks like a notepad on the top-left corner of your Stata viewer <sup><a href="#note-2" id="ref-2">[2]</a></sup>.

![]({{ '/assets/images/02.png' | relative_url }})

In the preliminary stages of your work, you may feel that a do-file is more hindrance than it is useful. For example, if you are not so familiar with a command, you may prefer to try it first. One simple way to do that and still have discipline about writing do-files is to write your do-file in stages, writing only a few commands before executing them, correcting mistakes as you go. In order to execute a number of commands rather than the whole do-file, simply highlight the ones you want to execute, and click on the “Execute Selection (do)” icon on the top of your do-file editor, at the far right.

![]({{ '/assets/images/03.png' | relative_url }})

As you become more proficient with programming in Stata, you won’t need to try out commands anymore, and you’ll discover the joy of writing a do-file and having it run without a glitch. To run a whole do-file, do not highlight any part of it and click on the “Execute Selection (do)” icon.

You may wonder about the commands “clear”, “set more off” and “set mem 15000” in the screenshot example. These three commands are administrative commands that are quite useful to have at the beginning of a do-file. The first, “clear”, is used to clear any previous dataset you may have been working on. The command “set more off” tells Stata not to pause or display the --more-- message. Finally, the command “set mem 15000” increases the memory available to Stata from your computer; here we will need it as the size of the data set we downloaded from Odesi <sup><a href="#note-3" id="ref-3">[3]</a></sup> is larger than the 10mb allocated to data by default.

One last comment about do files: if you double click a saved do file, it will not open for editing, but rather Stata will run that do-file, which can be a bit annoying… To reopen a do-file from a folder without executing the commands in it, right-click on it and select “edit” rather than “open”.

*Always keep a log*. Again, this is a general rule of thumb on Stata. Keeping a log means you can go back and look at what you did without having to do it again. Starting a log is just a matter of adding a command at the top of your do-file that tells Stata to log, as well as where you want the log to be saved:

log using “whateverpathyouwant:\pickanameforyourlog.smcl” <sup><a href="#note-4" id="ref-4">[4]</a></sup>, replace <sup><a href="#note-5" id="ref-5">[5]</a></sup>

Note how logs are saved under the smcl extension.

Do not forget to close your log before starting a new one. The last command on your do-file <sup><a href="#note-6" id="ref-6">[6]</a></sup> will usually be “log close”.

*Save as you go*. Computers crash, power goes out, stuff happens. Save your do-files every few minutes as you write them. Saving a do file is done the same way as saving any text editor document: either click on the diskette icon, or press “CTRL+S”:

![]({{ '/assets/images/04.png' | relative_url }})

You should also save your dataset as you modify it, but make sure to keep one version of the original dataset, in case you need to start over. The command to save a dataset on Stata is “save”, followed by the path where you want the dataset to be saved, and the [optional] command “replace”.

![]({{ '/assets/images/05.png' | relative_url }})

Note how the extension for Stata data is “.dta”, and also note how the new dataset has a different name from the original <sup><a href="#note-7" id="ref-7">[7]</a></sup>.

*Become familiar with your dataset*. Datasets come with codebooks. You should know what each variable is, how it’s coded, how missing values are identified. A good practice is to actually look at the data, so that you understand the structure of the information. To do so, you can click on “Data” in the top-left corner of your viewer and select Data editor, then Data editor (browse). A new window will open and you can see your data.

![]({{ '/assets/images/06.png' | relative_url }})

You can also use the command “browse”, either by typing it directly in the command window, or from a do file:

![]({{ '/assets/images/07.png' | relative_url }})

One of the distinguishing features of <odesi> is that when you download a dataset, it comes with labels. Variable labels are descriptions of variables, and value labels are used to describe the way variables are coded. Basically, the value label sits on top of the code, so that when you browse, you see what the code means rather than what it is. To make this clearer, let’s look at the data with no labels. Look, for example, at the GEOPRV variable.

![]({{ '/assets/images/08.png' | relative_url }})

---
<p id="note-1"><a href="#ref-1">[1]</a> There is an assumption here that you already have a dataset. If you do not and you need assistance assembling data, please visit the data library (THIS COMMENT NEEDS TO REFERENCE THE GUIDE ON HOW TO DOWNLOAD A DATASET FROM SDA)

<p id="note-2"><a href="#ref-2">[2]</a> You can use other text editors to create and manage do-files. For example, Smultron is an open-source software that works well with Stata. 

<p id="note-3"><a href="#ref-3">[3]</a> You can see the size of a data set by right-clicking on it, then selecting “properties”.

<p id="note-4"><a href="#ref-4">[4]</a> You should create a folder in an easy to remember location (desktop works well) for your Stata work. Then check its properties by right-clicking on it, and copy the location. That’s your path.

<p id="note-5"><a href="#ref-5">[5]</a> “,replace” is optional here but rather useful if you want to keep just one log per do-file. If you don’t have the “,replace” command, you will need to modify the name of the log every time you run the do-file.

<p id="note-6"><a href="#ref-6">[6]</a> However, if a do-file is interrupted because of an error and a log is open, you will need to close it before running the same do-file again, because one of the first command of the do file is to start a log, which will result in an error message unless the previous log is closed. Simply type the command “log close” in the command window, or highlight it and execute from your do-file.

<p id="note-7"><a href="#ref-7">[7]</a> Note to users of this guide: this command would typically be located towards the end of the do-file. I have created a screenshot here with a new do-file only to show one command alone. All the examples in this guide that similarly use a new do file with only one command were done that way to save space. The goal of this workshop is to learn to create a cleaning do file, in which commands are listed one after the other. I trust that users can understand the commands well enough by the end of the workshop to assemble them in the order that is logical for the purpose of their own task.