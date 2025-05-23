
# Reproducible Code



<img src="resources/images/07-code_files/figure-html//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g221fb1e0594_0_0.png" alt="Learning Objectives are to be able to: Find and utilize packages and their functions. Recognize aspects of reproducible code: Readable, Efficient, and Consistent. Work on code in a way that iteratively encourages the reproducibility of your project" width="100%" style="display: block; margin: auto;" />

## Reproducibility means we don't need to reinvent the wheel!

When you realize something that you need done, you should first use Google and look on GitHub and StackOverflow to see if someone else has written something that works really well. Where at all possible, borrow good code and attribute the author -- no need to reinvent the wheel. As we said previously, R has a great community of users who are constantly creating new and great code, often in the form of packages that are ready for you to install and use.

_This is the beauty of reproducibility, if you or someone else makes great code, it can not only be re-run but it can be repurposed!_

### Tips for choosing packages to use:

- Does the package have easy to use documentation to help guide you on how to use it properly? If the package has underdeveloped documentation it may be difficult for you or others to understand and use properly.
- Is the code actively being developed or maintained? Packages that are no longer being maintained will likely deprecate more quickly rendering them unusable in the future.
- Is it a package that is commonly recognized by the community? Well recognized packages will be easier for others to comment on and help you with.

## The importance of iterative work

We've mentioned previously that reproducibility is iterative work. This way of working refers to code work as much as anything else. You won't ever write perfect code on the first try, instead aim for each chunk to work one step at a time. Once it is working, take a break (perhaps until the next day), then return to it and look for ways to polish it and make it more efficient.

[For more tips on how to work read this blog](https://www.ccdatalab.org/blog/not-so-secret-sauce-for-efficient-workflows).

## Aspects of Reproducible code

<img src="resources/images/07-code_files/figure-html//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g221fb1e0594_0_6.png" alt="Reproducible code is: Readable meaning it is well-documented, uses well-known functions when appropriate, and follows a code style. Efficient meaning it doesn’t use up more computational resources than necessary and follows the advice of DRY (don’t repeat yourself). Consistent meaning it follows conventions and is organized" width="100%" style="display: block; margin: auto;" />

## Readable

Reproducible code is readable code. In order for other people to use your code, they will need to be able to understand it. Because of that, code being readable is more important than code being innovative or clever.

<img src="resources/images/07-code_files/figure-html//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed8021e09_2_120.png" alt="Reproducible parrot is looking at their computer and says ‘It’s so easy for me to understand what is going on with this code because it is so readable and follows a style!’" width="100%" style="display: block; margin: auto;" />

### Well-documented

Reproducible code is well documented code! This includes (but isn't limited to):

- A README that can get individuals up to speed on the project quickly
- Code and notebooks that have a healthy amount of comments

These bits of documentation are not only helpful for others reading your project but for you! As time passes, future you will forget what you of today was thinking when you wrote this code. Helpful code comments can help jog your memory of what the code is doing and perhaps what the next steps in the project need to be.

#### READMEs

READMEs are a universal signal to people looking at the project that they should READ this file to get a rundown on the project.

<img src="resources/images/07-code_files/figure-html//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g20ed8021e09_2_260.png" alt="Reproducible Parrot is looking at a set of project files that include a file called a ‘README.md’. The parrot says ‘I was so confused on where to start with this project but the README really brought me up to speed!" width="100%" style="display: block; margin: auto;" />

READMEs should include:

1. A summary of the goals and intentions of the project.
2. Usage instructions that explain exactly what commands and packages need to be used to re-run analyses.
3. Explanation of what software dependencies are needed for your project.
4. A basic summary of what files are there; which are input and output files.
5. Any other information that would be relevant to someone trying to understand the project.

Here's a [template README](https://raw.githubusercontent.com/jhudsl/Reproducibility_in_Cancer_Informatics/main/resources/README-template.md) that you can use an example.

<div class = "dictionary">
- **README** - A file in a project that has the start up summary information that could get someone acclimated to the project.
</div>

#### Code comments

A healthy amount of code comments doesn't mean that every line needs a comment (though perhaps at sections that need future explanation they might). Helpful code comments don't just echo what the code is doing but are explanatory. [StackOverflow has a great article](https://stackoverflow.blog/2021/12/23/best-practices-for-writing-code-comments/) about rules for writing helpful code comments. we'll echo the rules here:

> Rule 1: Comments should not duplicate the code.

> Rule 2: Good comments do not excuse unclear code.

> Rule 3: If you can’t write a clear comment, there may be a problem with the code.

> Rule 4: Comments should dispel confusion, not cause it.

> Rule 5: Explain unidiomatic code in comments.

> Rule 6: Provide links to the original source of copied code.

> Rule 7: Include links to external references where they will be most helpful.

> Rule 8: Add comments when fixing bugs.

> Rule 9: Use comments to mark incomplete implementations.

### Follows a code style

Code style helps make code readable. Appropriate spacing, punctuation, and grammar are not always essential for getting a message across, but it can certainly b3 dis-tRaCTIng to readers if conventions aren't followed.

**Basic Example:**

``` r
# Bad: Should use <- and have a variable name that is informative
x = c(1, 4, 5, 10)

# Bad: Irregular spacing is distracting
numbers<-  c(1, 4,5,10)

# Good!
numbers <- c(1, 4, 5, 10)
```

Here's some style guides you can use:

- [Google's R Style Guide](https://google.github.io/styleguide/Rguide.html)
- [Tidyverse Style Guide](https://style.tidyverse.org/index.html)

[R packages like styler](https://www.tidyverse.org/blog/2017/12/styler-1.0.0/) can automatically style code for you.


## Efficient

Reproducible code is efficient code. Efficiency helps reproducibility in that code that takes up less resources and is not redundant can be re-run and debugged more easily.

### Doesn’t use up more computational resources than necessary

R is not meant to be a fast language. R code can be computationally costly if it's written in the wrong way.

You can identify what parts of your R code are the slowest or otherwise computationally costly by using the [`profvis`](https://github.com/r-lib/profvis) and [`bench`](https://bench.r-lib.org/) packages.

One popular example is R loops which can be particularly slow in R. Note that this doesn't mean you shouldn't ever use loops or other items in R, just that you should be aware that some items in R are particularly slower than others.

**R 'for loop' alternatives:**

- [Using `apply` functions (an older option that comes with the basic installation of R)](https://statisticsglobe.com/avoid-for-loop-in-r)
- [Advanced R discusses alternative strategies](https://adv-r.hadley.nz/perf-improve.html?q=perfor#avoid-copies)
- [The across function](https://dplyr.tidyverse.org/reference/across.html)
- [Using the `purrr` package](https://purrr.tidyverse.org/)
- [A nice summary of these functions](https://jhudatascience.org/intro_to_r/modules/Functions/Functions.html#18)

**Further reading:**

- Hadley Wickham has a [great chapter in Advanced R](https://adv-r.hadley.nz/perf-improve.html?q=perfor#perf-improve) that covers these concepts in more detail.

### Is DRY (don’t repeat yourself)

DRY is an acronym for "don't repeat yourself". Non-redundant code is more reproducible because it is easier to maintain and to read.

Let's take a look at an example from [this Reproducibility in Cancer Informatics course](https://jhudatascience.org/Reproducibility_in_Cancer_Informatics/writing-durable-code.html#dry-up-your-code) about what DRY vs non-DRY code might look like:

Non-DRY or WET (write everything twice) code might look like this:
```
paste('Hello','John', 'welcome to this course')
paste('Hello','Susan', 'welcome to this course')
paste('Hello','Matt', 'welcome to this course')
paste('Hello','Anne', 'welcome to this course')
paste('Hello','Joe', 'welcome to this course')
paste('Hello','Tyson', 'welcome to this course')
paste('Hello','Julia', 'welcome to this course')
paste('Hello','Cathy', 'welcome to this course')
```

Note that if you want to change something in eight of these messages you would have to change all eight lines.

To DRY up this code, we could functionalize it:
```
GreetStudent <- function(name) {
 greeting <- paste('Hello', name, 'welcome to this course')
 return(greeting)
}

class_names <- c('John', 'Susan', 'Matt' ,'Anne', 'Joe', 'Tyson', 'Julia', 'Cathy')

lapply(class_names, GreetStudent)
```

Now, if we wanted to edit the greeting pasted, we'd only have to change it once.

<div class = "dictionary">
- **DRY code** - Code that doesn't repeat itself and because of that is more efficient
</div>

## Consistent

Consistency is key for reproducibility. Not only do we want code to run consistently, but it will be more understandable to our future selves and to others if it follows a pattern.

### Follows conventions

Although there's always a time to break conventions, often times conventions lend to readability. For example, in R using `<-` for assignments is less likely to be distracting than using `=`. This is related to following a style guide. In general we recommend using the tidyverse conventions and style.

However, this advice, like a lot of the advice in this chapter is highly dependent on the context and goals of the project and code being written. There are times that the conventional way to write something might not suit the project because it is inefficient or otherwise clashes with other goals of reproducibility.

### Is organized

In the previous chapter, we discussed how projects should be organized in order to be reproducible, but this also applies to code. Sometimes as you have been working on code, you may realize that as it has been developing it doesn't flow in an organized manner.

Just as with regular writing that is disorganized, code that is disorganized can be hard to follow and hard to bug. For example, if you have hard coded a multiple variables or have loaded multiple packages, it makes sense to group these items together so they are easier to find and fix.

A code outline for an analysis notebook for example might look like:

- Describe the goals
- Load in the libraries and any source code
- Declare any hard coded variables
- Read in the data  
- Clean the data
- Make plots and gather statistics
- Summarize results
- Print out the [session info]() we'll discuss more about this in a future chapter.

## Conclusion

The best way to find out if your code meets these concepts or how it can better become more reproducible is through code review. We will briefly discuss code review in future chapters.

In summary, reproducible code is:

- Readable
  - Well-documented
  - Follows a code style
- Efficient
  - Computationally non wasteful
  - DRY
- Consistent
 - Follows convention (when appropriate)
 - Organized
