---
layout: single
author_profile: false
title: "Introduction to R"
classes: wide

sidebar:
  nav: "sessions"

---

## Week 1

**Zoom Link:** [https://ualberta-ca.zoom.us/j/97755262261](https://ualberta-ca.zoom.us/j/97755262261)

Welcome to the first week of content! Topics of this week will be an introduction to this series, an overview of Object-Oriented Programming (OOP) and some of the basic programming skills that will form the basis of what we'll learn from here on out.

{% include video id="gxQLZV-qdXw" provider="youtube" %}


Please watch the below videos **before** coming to the synchronous lecture - they are relatively short. Follow along when asked, and write down any questions or difficulties you have that we can discuss in lecture.

### Step 1 - Software Downloads

Ah yes, the dreaded first step! Our first workshop is approaching, and to maximize our time together, we ask that you please come prepared with the necessary software downloaded. Please follow these instructions carefully and if you run into problems you can't solve, please reach out and we'll do our best to help you out.

#### Windows
If you already have R and RStudio installed
* Open RStudio, and click on “Help” > “Check for updates”. If a new version is available, quit RStudio, and download the latest version for RStudio.
* To check which version of R you are using, start RStudio and the first thing that appears in the console indicates the version of R you are running. Alternatively, you can type `sessionInfo()`, which will also display which version of R you are running. Go on the CRAN website and check whether a more recent version is available. If so, please download and install it. You can [check here](https://cran.r-project.org/bin/windows/base/rw-FAQ.html#How-do-I-UNinstall-R_003f) for more information on how to remove old versions from your system if you wish to do so.

If you don’t have R and RStudio installed
* Download R from the [CRAN website](http://cran.r-project.org/bin/windows/base/release.htm).
* Run the `.exe` file that was just downloaded
* Go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download)
* Under Installers select RStudio x.yy.zzz - Windows Vista/7/8/10 (where x, y, and z represent version numbers)
* Double click the file to install it
* Once it’s installed, open RStudio to make sure it works and you don’t get any error messages.
#### macOS
If you already have R and RStudio installed
* Open RStudio, and click on “Help” > “Check for updates”. If a new version is available, quit RStudio, and download the latest version for RStudio.
* To check the version of R you are using, start RStudio and the first thing that appears on the terminal indicates the version of R you are running. Alternatively, you can type sessionInfo(), which will also display which version of R you are running. Go on the CRAN website and check whether a more recent version is available. If so, please download and install it.

If you don’t have R and RStudio installed
* Download R from the [CRAN website](http://cran.r-project.org/bin/macosx/)
* Select the .pkg file for the latest R version
* Double click on the downloaded file to install R
* It is also a good idea to install [XQuartz](https://www.xquartz.org/) (needed by some packages)
* Go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download)
* Under Installers select RStudio x.yy.zzz - Mac OS X 10.6+ (64-bit) (where x, y, and z represent version numbers)
* Double click the file to install RStudio
* Once it’s installed, open RStudio to make sure it works and you don’t get any error messages.
Linux
* Follow the instructions for your distribution from [CRAN](https://cloud.r-project.org/bin/linux), they provide information to get the most recent version of R for common distributions. For most distributions, you could use your package manager (e.g., for Debian/Ubuntu run sudo apt-get install r-base, and for Fedora sudo yum install R), but we don’t recommend this approach as the versions provided by this are usually out of date. In any case, make sure you have at least R 3.3.1.
* Go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download)
* Under Installers select the version that matches your distribution, and install it with your preferred method (e.g., with Debian/Ubuntu sudo dpkg -i rstudio-x.yy.zzz-amd64.deb at the terminal).
* Once it’s installed, open RStudio to make sure it works and you don’t get any error messages

In future weeks, we'll have a few videos for you to watch that have programming concepts or ideas presented, that we will then practice in our synchronous session. This week, we are just getting you set up to be ready to code, and we'll do everything else together in our session! Looking forward to seeing you all soon!

### Introduction to This Series

We want to give you an idea of what this series is for, and how to get the most out of it. Please watch this video where Emma will tell you about what you'll learn and (maybe more importantly!) what you **won't** learn.

**THIS VIDEO WILL BE LIVE AFTER 12PM MT MONDAY, OCT. 05**

{% include video id="iktRaJMu4gA" provider="youtube" %}

### Using RStudio

In this video, Cole will give you a walkthrough of RStudio, so make sure you have R and RStudio downloaded, following the instructions above. Open RStudio and follow along on your own computer. Make a note of any questions you have and we can discuss them in the live session!

{% include video id="zVZK2J9hMwA" provider="youtube" %}

### OOP & Objects in R

Object-Oriented Programming (OOP) is the lens through which we'll approach everything we do in R. Inherent to the principles of OOP is that everything in R is an object. In this video Cole will walk you through the basics of objects and types in R. This will become important later, and we will spent most of the live session practicing using different types of objects in R. Make a note of any questions you have and we can discuss them in the live session!

{% include video id="Ytcr2Nr6lYU" provider="youtube" %}

-----------------------------
Please [click here](https://forms.gle/eu9LVRrNmfToRC2fA) to fill out the post-session feedback form here! We take your feedback into account in real time, so any changes we can make to help you learn better next week we will make!


# Content Summary

<embed src="https://colebrookson.github.io/r-for-biology/sessions/week1_pdf.pdf" type="application/pdf" />

### Reading Data Into R

Here is a summary video of reading data into R and performing basic operations.

{% include video id="HK5uXRjEers" provider="youtube" %}

**At Home Practice:** If you want some more practice with the concepts we've worked on here, try the following problems. Keep in mind that there is usually more than one way to achieve a particular result, so there is no 'right' way, but try and use the concepts/principles we talked about in this session.

1. Create a list of float values of length 10 called 'useful_list'
2. Create a fake dataframe with 10 rows and 3 columns. Make one column float values called 'useful_column'
3. Add the list of integers to the dataframe as a new column
4. Make a new column in the dataframe with the mean value of the columns 'useful_list' and 'useful_column'. Call this new column 'useful_mean'.

Try and come up with a solution to this that only uses <7 lines of code.
