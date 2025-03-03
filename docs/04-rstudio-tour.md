
# A Tour of RStudio

In this chapter we will talk about a very useful R-related tool called RStudio. RStudio is an environment for using R that can be extremely helpful for writing code and making your analyses reproducible.


![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g21a84b32106_0_0.png){width=100%}

## Why use RStudio?

RStudio is what is called an **integrated development environment (IDE)** for writing code in R (although it also has compatibility for other languages).

It is designed to make working in R easier in a variety of ways by helping you:

- write code by using suggestions to complete what you have written - currently this is mostly for suggesting package names or functions (which are specific pieces of code that accomplish a particular task, often packages have several functions)
- view the output of your code, this is especially true for creating reports or viewing plots
- find errors in your code
- keep track of any objects that you have assigned in R
- orient yourself in terms of the files on your computer
- track changes in your code and other files over time


<div class = "dictionary">

- **IDE** - Integrated Development Environment - a computing environment for writing code, debugging code, and looking at the output of your code
- **RStudio** - an IDE designed especially for writing R code
- **function** - a specific piece of code that performs a task - packages in R often have several functions
- **objects** - objects in R could be anything that you can refer to with some name to recall again such as a data tables, vectors, functions, plots and more.

</div>

We will dive deeper into these benefits later once we get started with RStudio, but first we will discuss how to make sure you have it downloaded and installed on your computer.

## Installing RStudio

In case you don't yet have RStudio on your computer, we will walk you through the process of getting started.

### Installing and Updating R

You first need to make sure that you have R. R is not the same as RStudio. R is instead the libraries needed to use R code on your computer and it is needed so that you can use RStudio. It is also a good idea to update the version of R that you are using periodically.

<details> <summary> Click here for directions if you have never installed R before on your computer. </summary>

You can install the latest version of R from the R project site located here: https://www.r-project.org/

From here you can click on the menu option that says CRAN on the far left to start. Recall that CRAN stands for the **Comprehensive R Archive Network**.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_0.png){width=100%}

This will take you to a website with a list of what are called [mirrors](https://cran.r-project.org/mirrors.html), which are locations that have the same exact copy of R but are dispersed geographically mostly to improve download speeds for users. Nothing bad will happen if you click on a mirror that isn't closest to you, but it can improve download speeds for everyone overall if people use appropriate mirrors.


![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_11.png){width=100%}

Once you click on one of the mirror links you will be taken to a new page to download R. For example, you could click on the Iowa state University mirror if you are located in the US somewhere.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_19.png){width=100%}

You would want to click on the appropriate link for your computer. For example, if you have a Windows machine, click the link for Windows.

This will take you to a new page to select the appropriate link to download R. For Mac users this might be the most recent version of R which will look like R and several numbers afterwards.

</details>

<details><summary>Click here for instructions on how to update R.</summary>

To update R, if you are using a Mac or Linux computer, you can follow the directions of installing R the first time.

If you have a Windows computer, you can use the following code to update your version of R within an R session. You can start an R session by typing `R` into Command Prompt window. If you have not used the Command Prompt window, [read instructions here](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/) about how to find it. After opening your Command Prompt window, copy and paste this code and press enter.


``` r
# Check for the install r package and install if needed
if(!require(installr)) {
  install.packages("installr");
  require(installr) #load installr pakage
}

updateR()#update your version of R
```

</details>

### Installing RStudio

Next we want to download and install RStudio. You can do so by going to the Posit website at this link: https://posit.co/. Note that you can likely accomplish all you need with the completely free option.

<div class = "notice">

Posit is a software company that used to be called RStudio that develops open-source data science tools and packages. It is a Public Benefit Corporation (PBC) and a Certified B Corporation®, so it is committed to creating software that benefits the public. See [here](https://posit.co/about/pbc-report/) for more information.

</div>

<details><summary> Click here for instructions on how to download and install RStudio. </summary>

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_30.png){width=100%}
Note that the website may look slightly different when you visit it.

There should be a download button on the upper right corner. This will take you to another page to choose if you want the free or paid version of RStudio. The free version should be enough for most users.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_37.png){width=100%}

Then you need to scroll down to select the appropriate download for your computer based on what kind of computer you have.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_37.png){width=100%}

Note that by the time you read this the versions will likely have changed and there may be slight variations in how the website appears.

You should then be directed by your computer on how to install RStudio once the download is complete. You may need to go to your downloads first and click on the RStudio file that was downloaded to start this process.

For Mac users, note that you will need to move the RStudio icon into the icon that looks like the Applications folder.


Drag and drop RStudio into the Applications folder to install on a Mac

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_58.png){width=100%}

See[here](https://jhudatascience.org/intro_to_r/modules/RStudio/RStudio.html#1) for more information on the process of installing RStudio.

If you run into trouble, check the following:

- Did you install the correct version of software for your operating system?
   - Check that you installed the version right for your type of system, (`macOS` vs `Windows` for example)
   - Check if maybe you need a different version for the age of your system. First check that your version of R was right - there are multiple versions for different `macOS` systems for example. You can check the apple icon (top left corner) and "About This Mac" to learn more about the age of your operating system.

If your operating system is older (and you can't update it), try installing progressively older versions found [here](https://www.rstudio.com/products/rstudio/older-versions/) until it works. You will know if it worked if you try to open RStudio and you see an interface without a message about things going poorly. Here you can see an [example](https://community.rstudio.com/t/rstudio-desktop-crashes-on-startup-with-library-not-loaded/130296) of this.

</details>

### Updating RStudio

It is also a good idea to keep RStudio up-to-date. New features become available as the Posit team works on developing RStudio. So if you already have RStudio, you might want to check to see if your version is up-to-date.

To check for updates you can go to the `Help` menu at the top of RStudio and then click on `Check for Updates`.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_50.png){width=100%}


If you don’t need to update RStudio, when you check with this method RStudio will let you know that you are using the newest version.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g229ab7a949e_0_557.png){width=100%}

With recent versions RStudio will also give you a popup to let you know that you could update.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g229ab7a949e_0_563.png){width=100%}



## Navigating RStudio

Now that you hopefully have RStudio running on your machine, we will walk you through some of the major features that can really help you with your data analyses.

### Default Layout

First it is important to be familiar with the layout. When you first open RStudio, you will see 3 panes.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_67.png){width=100%}

<details><summary>If your RStudio looks different click here.</summary>

Click on the top menu of your RStudio - click where it says `Edit` --> `Preferences` --> `Pane Layout`.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g22370a5f292_430_0.png){width=100%}

The Pane Layout menu enables you to change the layout. The image below shows the default settings. Note that VCS may not appear if you are not using a version control system. More on that to come in later chapters!

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g22370a5f292_430_5.png){width=100%}

</details>


The pane on the left (labeled "Pane 1" in the image) is where we can work on code interactively. There are two tabs here. The Terminal tab and the Console tab. The Terminal tab is for interacting with the computer outside of R. Whereas the Console tab is for interacting with R. We'll focus on the Console tab for now.

The Console tab is where we can 'talk' to R and interactively work on our code. The code we write here will **not be saved** to a script or file, but instead the code will immediately be performed when we click `enter` and any resulting output that can be printed will be shown.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_81.png){width=100%}

The pane on the top right (labeled "Pane 2" in the image) is where we can see what objects we have created and are actively in memory (meaning they can be used at that time) in what is called the "Environment".

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_95.png){width=100%}


The pane on the bottom right (labeled "Pane 3" in the image) is where we can find files on computer (the "Files" tab), see plots (the "Plots tab), and get coding help (the "Help tab).

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_109.png){width=100%}


While there are other tabs, don't worry about those for now. We will go deeper into RStudio as we continue.


Let's try some examples to get started.

As an example, we could type in the code `head(iris)` into Pane 1 in the Console and press the `enter` key to see the code execute and preview.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_142.png){width=100%}

Now let's try another example where instead of just printing some data to the screen we assign a data object that will show up in the environment using the `<-` notation. This is useful in a situation if we want to modify the iris data somehow but want to keep the original version.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g1fa1583c827_0_4.png){width=100%}


<div class = "dictionary">
- **Console** - The window that allows us to interactively give R code and press enter to run it but **not save** the code.
- **Environment** - R's working memory of objects you have assigned -- need to tell R to remember using `<-`
- **Assignment** - How we tell R to remember something using the `<-` characters.
</div>

### The Hidden Pane

There is a hidden fourth pane. This is only accessible when we start to make a script or a report with our code. This is where we recommend that you write your code - as this is where we will save our code! If you get used to writing most of your code in the Console, you might forget what code actually worked. Additionally, as we are trying to make our code reproducible, it's a good idea to start saving it as we write it!

To open this let's make what is called an R Markdown file by go to `File` --> `New File` -->`R Markdown` in the upper menu of RStudio.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_127.png){width=100%}

Creating an R Markdown file starts with a pop-up and you can simply click the OK button.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_169.png){width=100%}

The new pane will open on the upper left.


![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_176.png){width=100%}

This pane is where we can write code that we keep in files like scripts or reports (in files like R Markdowns).

Thus the lower left pane is where we can test out code (although we don't recommend it), but the top pane is where we can write code that we wish to save (and also test it!). Since it can be easy to forget to save code, we suggest that instead you use a special file type that will allow you to test code that you save. We will discuss that in the next section.

In order to make our analysis truly reproducible we will need to have **every single step** written down. This is why using the Console is great for testing things, but not so great for actually performing your analysis.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_186.png){width=100%}

The top pane where we save code is called the Editor. The lower pane for quick tests of code is called the Console.

![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed7630a13_1_198.png){width=100%}

The Editor pane (top left) will be the pane that we look at most of the time as we create reports that demonstrate exactly how we did our analyses. We will discuss more about R Markdown files in the next section.

R Markdown files allow you to have the code for your analysis, the output from the analysis (so plots and stats, etc) and your written thoughts and rationale for your analysis all in one place! This makes it a snap to share your analysis with others in a reproducible way!

<div class = "dictionary">

- **Console** - for quickly testing code, the code is not saved. This is by default the lower left pane when a file is open in RStudio. Testing of code here does not have some features that testing in an R Markdown file has so we don't generally recommend it.
- **Editor** - for writing code that you wish to save.
- **R Markdown files** - files that allow you to save your code that allow for more features than a simple script.

</div>

## Find Errors

Another nice thing about RStudio, is that it can help you troubleshoot your code.

It helps to identify common coding mistakes. It will indicate a potential problem by showing a red circle with an "x" in it on the far left of the Editor near the line of code that it thinks is problematic. Note that sometimes errors may occur earlier in your code than where RStudio starts to notice an issue.


Here is an example of such a case. Here we have an extra parentheses in our code.


![](04-rstudio-tour_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g219ee06dc74_531_0.png){width=100%}

Note that just because RStudio thinks your code is free of errors, it does not necessarily mean that your code is correct. RStudio can detect certain syntax issues, but it does not detect all types of errors. However, you can probably see how it could be very helpful!


## Keyboard Shortcuts

There are lots of useful keyboard shortcuts for RStudio that can save you time.

Check out this [link](https://support.posit.co/hc/en-us/articles/200711853-Keyboard-Shortcuts) if you are interested!

The most helpful shortcut, is for testing a selection of code in an R Markdown file using a keyboard shortcut of Ctrl+Enter on Windows & Linux computers or Cmd+Return on Mac computers.

## Conclusion

In summary...

- RStudio can help you write code in R and work with files on your computer.
- There are 3 main panes when you first open RStudio, to see a fourth you need to create a new file like an R Markdown file.
- When we open a file like an R Markdown file, the top left pane called the Editor is for writing code we wish to save.
- After opening a file, the lower left pane contains the Console which is where we test code.
- R Markdown files are files that create reports of an analysis that can demonstrate more about what you did than a simple script and test to make sure that your code works.
