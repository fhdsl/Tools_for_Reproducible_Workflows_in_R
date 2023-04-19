
# Software versions



## Learning Objectives

![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g21a84b32106_0_43.png){width=100%}

As we discussed, reproducibility is on a continuum, meaning that it can range from being impossible to very easy to reproduce any given results. Some results can be effectively impossible to reproduce if there are too many barriers and set up needed to re-run the analysis. One of the most common barriers is the computing environment used run the analysis.

<div class = "dictionary">
**computing environment** - All the relevant pieces of software and their dependencies that were used on a computer at the time that an analysis or other project was run
</div>

## No two computers are the same

A computing environment not only consists of the direct software that we use to analyze data, but all of the other software that our main pieces of software require to install and run properly.

As we use our computers daily for work, we are constantly installing, updating, and removing software packages. Sometimes our computers do this automatically without us knowing. These software packages interact with and depend on each other, meaning it can be quite frustrating to try update even a single piece of software if it exists in a tangled mess of software dependencies. Computer scientists sometimes call this "[dependency hell](https://en.wikipedia.org/wiki/Dependency_hell)".

![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g21dfe2f76f9_90_50.png){width=100%}

As developers and maintainers of software continue to make updates and fixes to the software, the developers and maintainers of other interdependent software are doing similarly, meaning that software dependencies and the computing environments are not only a complicated mess at times, but also a moving target!

## Software and package versions affect results!

Sometimes if we have generally the same software installed for reproducing an analysis, we may feel that that is "close enough". And given all the other technical aspects of reproducibility, it can be easy to overlook what versions of software packages we are using. However, controlling for software versions is critical for creating reproducible analyses. Software versions can directly affect not only whether an analysis will be able to run, but the results of the analysis [@BeaulieuJones2017].

## Session Info

Perhaps the easiest way to begin to address computing environment variability is to record what the computing environment looks like at the time an analysis is run. In R, this is a fairly straightforward task.

Generally at the end of your R notebook, you will want to print out your session info. You can do this by running the function `sessionInfo()` or the tidyverse version of this function from the devtools package, `devtools::session_info()`.

We can run `sessionInfo` in this book (this book was created using R tools).


```r
sessionInfo()
```

```
## R version 4.0.2 (2020-06-22)
## Platform: x86_64-pc-linux-gnu (64-bit)
## Running under: Ubuntu 20.04.5 LTS
## 
## Matrix products: default
## BLAS:   /usr/lib/x86_64-linux-gnu/openblas-pthread/libblas.so.3
## LAPACK: /usr/lib/x86_64-linux-gnu/openblas-pthread/liblapack.so.3
## 
## locale:
##  [1] LC_CTYPE=en_US.UTF-8       LC_NUMERIC=C              
##  [3] LC_TIME=en_US.UTF-8        LC_COLLATE=en_US.UTF-8    
##  [5] LC_MONETARY=en_US.UTF-8    LC_MESSAGES=en_US.UTF-8   
##  [7] LC_PAPER=en_US.UTF-8       LC_NAME=C                 
##  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
## [11] LC_MEASUREMENT=en_US.UTF-8 LC_IDENTIFICATION=C       
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## loaded via a namespace (and not attached):
##  [1] knitr_1.33      magrittr_2.0.3  hms_0.5.3       R6_2.4.1       
##  [5] rlang_1.1.0     fastmap_1.1.1   fansi_0.4.1     stringr_1.4.0  
##  [9] httr_1.4.2      tools_4.0.2     xfun_0.26       utf8_1.1.4     
## [13] cli_3.6.1       htmltools_0.5.5 ottrpal_1.0.1   yaml_2.2.1     
## [17] digest_0.6.25   tibble_3.2.1    lifecycle_1.0.3 bookdown_0.24  
## [21] readr_1.4.0     vctrs_0.6.1     fs_1.5.0        curl_4.3       
## [25] glue_1.4.2      evaluate_0.20   rmarkdown_2.10  stringi_1.5.3  
## [29] compiler_4.0.2  pillar_1.9.0    pkgconfig_2.0.3
```

Now we have recorded what some key aspects of our computing environment looked like at the time that this book was rendered last.
This print out may seem like a lot of nonsense at first, but it gives us some useful information in a pinch!


![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g201bd406763_37_1030.png){width=100%}

If we take a look at two different session info printouts, we can begin to spot the differences. These differences may give us clues into why an analysis ran differently.

![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g201bd406763_37_1333.png){width=100%}

Printing out session info is an easy way to record your computing environment in hopes of increasing the reproducibility of your analysis!

<div class = "dictionary">
**session info** - A printout in R that displays information about the software and packages that were being used at the time the `sessionInfo()` or  `devtools::session_info()` functions were run.
</div>

## Snapshots with `renv`

However, you may realize that while session info is useful for recording this information, it doesn't mitigate the frustration of setting up a computing environment in R. Nor does it help us with being able to directly share our computing environments.

It can be incredibly handy for reproducibility purposes to be able to share the R computing environment you used for completing an analysis. This is not only helpful for others who may be interested in reproducing your analysis, but also for future you! If you come back to this analysis and attempt to re-run it, it is likely you've changed your R computing environment over time by installing or removing packages. `renv` will allow you to return to the environment you used at the time that you ran the analysis. 

For that, we need a slightly more involved solution of using [`renv`](https://rstudio.github.io/renv/articles/renv.html). `renv` is an R package that allows you to take 'snapshots' of your R computing environment and use those to track, share, and build R environments.

![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g201bd406763_37_1492.png){width=100%}

The `renv` workflow looks like this (as described by their documentation):

> 1. Call `renv::init()` to initialize a new project-local environment with a private R library

> 2. Work in the project as normal, installing and removing new R packages as they are needed in the project

> 3. Call `renv::snapshot()` to save the state of the project library to the lockfile (called renv.lock)

> 4. Continue working on your project, installing and updating R packages as needed

> 5. Call `renv::snapshot()` again to save the state of your project library if your attempts to update R packages were successful, or call `renv::restore()` to revert to the previous state as encoded in the lockfile if your attempts to update packages introduced some new problems

To make this shareable to others, you will need to do two things:

1. Be sure to commit and push the `renv.lock` file to your GitHub repository for your project.
2. Be sure to describe that your project uses `renv` in the README of this project (commit and push this to your GitHub repository also).

![](resources/images/08-software-versions_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g21dfe2f76f9_90_163.png){width=100%}

The limitations of this method, [as noted by the `renv` authors](https://rstudio.github.io/renv/articles/renv.html#caveats), is that it really only tracks packages in R and cannot help track or enforce items that may affect the computing environment outside of R. So while it will aid in the reproducibility of your analysis, it will not cover everything.

<div class = "dictionary">
**renv** - An R package that helps you to share and record your R specific computing environment
</div>

## Containerization

In order to truly reproduce a result with an identical computing environment you would need to use a containerized approach. To containerize a computing environment is to truly create an environment that is shippable to others. A container is analogous to a virtual machine. A computer runs a computing environment inside of it that is separate from the rest of the computer (hence why its called a container).

One of the most popular containerization softwares is Docker. Docker allows you to build your computing environment and share it on its online platform in the form of images that you can download and run. In fact, this book is rendered by a Docker container!

<div class = "warning">
If you will be using a container with PHI or PII or other protected information, we recommend you take a look at [this resource](https://www.cleardata.com/wp-content/uploads/2017/07/SET-MKTG-WP-36_HIPAA_Compliant_Containers_05-04-2017.pdf) to understand best practices for using Docker with sensitive data.
</div>

<div class = "dictionary">
- **container** - A method for running software in a way that is shareable and Reproducible
- **Docker** - A popular platform for containers
</div>

We will not cover Docker here but if you are interested in using a containerized approach like Docker, here are additional resources for learning:

- [Software Carpentries course on Docker](https://carpentries-incubator.github.io/docker-introduction/introduction/index.html)
- [ITCR Training Network chapters about Docker](https://jhudatascience.org/Adv_Reproducibility_in_Cancer_Informatics/launching-a-docker-image.html)
- [Docker documentation about getting started](https://www.docker.com/get-started/)
- [How to ensure your Docker usage is HIPAA-Compliant](https://www.atlantic.net/hipaa-compliant-hosting/best-practices-for-creating-a-hipaa-compliant-docker-host/)
- [HIPAA Compliant Containers](https://www.cleardata.com/wp-content/uploads/2017/07/SET-MKTG-WP-36_HIPAA_Compliant_Containers_05-04-2017.pdf)
- [Singularity is a different container platform that does some encryption](https://docs.sylabs.io/guides/latest/user-guide/) -- this can help if you are using data that needs to be protected.

## Conclusion

In summary:

- Software versions affect the reproducibility of an analysis.
- Printing out session info is a great way to record software versions.
- `renv` is an R package that allows you to share your R specific computing environment.
- Containerization softwares like Docker allow you to more completely share a replicate computing environment.
