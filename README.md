# Overview

A template file and folder structure for a data analysis project/paper done with R/Quarto/Github. Other components (e.g., other programming languages) can be added as needed. 


# Pre-requisites

This is a template for a data analysis project using R, Quarto, Github and a reference manager that can handle bibtex. Our recommendation for the reference manager is Zotero, with the Better BibTex plugin/extension. It is also assumed that you have a word processor installed (e.g. MS Word or [LibreOffice](https://www.libreoffice.org/)). You need that software stack to make use of this template.


# Template structure

* All files created from other sources (e.g. bibliography, pdfs, schematic figures that were manually generated) go into the `assets` folder and subfolders.
* All code goes into the `code` folder and subfolders.
* All data goes into the `data` folder and subfolders.
* All products (manuscripts, supplement, presentation slides, web apps, etc.) go into `products` folder and subfolders.
* All results (figures, tables, files with computed values) go into the `results` folder and subfolders.
* The `renv` folder is automatically generated by the `renv` package and you
should never edit it manually. This folder is used to store information about
the packages you are using in your project.


# Naming conventions

We try to follow these naming conventions for folders and files: 

* Somewhat descriptive and easy to understand names.
* Only lower-case letters (and numbers if needed), words separated by a `-`. 

For instance there is a folder called `analysis-code` with a file called `exploratory-analysis-v2.qmd` in it. We don't use `_` or blank spaces for separators. We also don't use CamelCase, only lower-case. Exceptions are made for standard file endings, for instance R scripts end in `.R` (instead of `.r`).



# Template content 

The template comes with a few files that are meant as illustrative examples of the kinds of content you would place in the different folders. See the `readme` files in each folder for more details.

* There is a simple, made-up dataset in the `raw_data` folder. 
* The `processing_code` folder contains several files that load the raw data, perform a bit of cleaning, and save the result in the `processed_data` folder. 
* The `analysis_code` folder contains several files that load the processed data, do an exploratory analysis, and fit a simple model. These files produce figures and some numeric output (tables), which are saved to the `results` folder.
* The `results` folder contains code output, including figures, tables saved as serialized R data (`.Rds`) files, and other outputs (distinct from data because they are generated by code).
* The `assets` folder contains static assets like pre-generated schematics from BioRender, bibtex files, csl files, and PDFs of references. These assets are not code-based and are not generated by code.
* The `products` folder contains final deliverables, like slides, the manuscript/report, the supplement, and posters.
  * The  `manuscript` subfolder contains a template for a report written as Quarto file. If you access this repository as part of [my Modern Applied Data Science course](https://andreashandel.github.io/MADAcourse/), the sections are guides for your project. If you found your way to this repository outside the course, you might only be interested in seeing how the file pulls in results and references and generates a word document as output, without paying attention to the detailed structure. There is also a sub-folder containing an example template for a supplementary material file.
  * The `slides` subfolder contains a basic example of slides made with Quarto.
* There are multiple special files in the repo.
  * `readme.md`: this file contains instructions or details about the folder it
  is located in. You are reading the project-level `README.md` file right now.
  * `renv.lock`: a special file in JSON format used to keep a log of which
  packages and versions your project uses. Don't edit by hand.
  * `.gitignore`: this file gives instructions to the version control system,
  Git, and tells it which files we do not need to record versions of. Usually
  these are various files containing local settings. Sometimes you might want to edit this.
  * `.Rprofile`: whenever you restart the R session, R will source (run all
  code in) this script. Right now this is used by `renv` to make sure we have
  the correct packages and versions installed. Don't edit by hand.


# Getting started

This is a Github template repository. The best way to get it and start using it is [by following these steps.](https://help.github.com/en/articles/creating-a-repository-from-a-template)

Once you got the repository, you can check out the examples by executing them in order. First run the processing code, which will produce the processed data. Then run the analysis scripts, which will take the processed data and produce some results. Then you can run the manuscript, poster and slides example files in any order. Those files pull in the generated results and display them. These files also pull in references from the `bibtex` file and format them according to the CSL style.

Tracking of R packages is done with `renv`. You should read [the introduction to `renv` article](https://rstudio.github.io/renv/articles/renv.html) so you know how to use it.

Since this template is already initialized with `renv`, you don't need to do that part again. Once you made a new repo from this template and cloned to your computer, you can get all the packages that are currently used by running `renv::restore()`.

As you install new packages (using `renv::install()`), you want to track them with `renv::snapshot()`. Once you read through the `renv` documentation it should be fairly clear how to use things.



