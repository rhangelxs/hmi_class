# Contributing to HMI course
:+1::tada: First off, thanks for taking the time to contribute! :tada::+1:

The following is a set of guidelines for contributing to my course, which are hosted on GitHub. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

#### Table Of Contents

<!--[I don't want to read this whole thing, I just have a question!!!](#i-dont-want-to-read-this-whole-thing-i-just-have-a-question)-->

[Project](#project)
  * [Code of Conduct](#code-of-conduct)
  * [Project Conventions](#project-conventions)
  * [File structure](#file-structure)
    * [Root folder name](#root-folder-name)
    * [File names](#file-names)
  * [Uploading your project](#uploading-your-project)
    * [Pull request](#pull-request)

## Project

### Code of Conduct

Good rule here is **not to harm**.

* Respect copyright, if parts of your project using something - cite it.
* If you made any conclusions check it twice.
* ...

### Project Conventions

There are a few conventions that have developed over time.

First, bear in mind, that you should make a significant decision how you will publish and maintain the project files, what you should or shouldn't publish.

As of 2017 projects consists up to four parts, called: `report`, `dataset`, `script` and `presentation`. Each part should be placed in separate file.
Role of each part will be described below.

Suggested file structure provided [file structure](#file-structure) section.

* :blue_book: **Report** is typically describe experimental design and details of realization of the research project. Basically it is text file, but you can include any support materials if it is needed.
	* Try not to add too much though, stay clear.
	* At the same time, add **all** needed description, procedures and materials here.

* :bookmark_tabs: **Dataset** includes all original data in tabular form.

  Check that:
	* You upload data in raw format (not aggregated)
	* Double check columns header fit to your variables
	* Units for every variable is clear
	* Numerical data is machine readable
* :computer: **Script** file contains checking of your assumptions, analysis and result of it.
	* Script can be published in two types: *original code* and *compiled one*. Compiled version is human readable and published in exchangeable formats like HTML, Markdown or others.
		> **Note.** Jypyther Notebook contains both code and output, so it might be upload as is.

	* You can choose: include **both versions** (included the original code), or if you prefer, didn't publish your code.
	  
	  If you publish your code, please double check that it will run with new file structure!
	  
	  > The best way to test it — is moving files from old location and check for any compilation errors.

	* Please, always include **compiled version of your script**. Compiled or human readable means any output of your script (even in txt). Because nobody should have the same libraries as yours on they machines.

* :sunrise_over_mountains: **Presentation** is essential results that you got in short visual form.
	* Printable version of you presentation is the best option to publish.

### File structure

File structure is important.

We will document it in this file. If you have a question around how to do things, check to see if it is documented here. If it is not documented there, please ask your question.

First, please be noted that your project root folder will be located under [github.com/rhangelxs/hmi_class/projects/current_year/](github.com/rhangelxs/hmi_class/projects/)

#### Root folder name

Please name your root folder using comma separated surnames of the author's. So it will looks `Petrov, Sidirov`.

> **Note**. Please don't use short name of project in folder name. It should be used in filename (see [Filenames section](#file-names), option 2).

#### File names

All files should have a valid extension according to the filetypes.

According to filenames, two main options are available:

1. Using **same common name** for all project files: :blue_book:, :bookmark_tabs:, :computer:, :sunrise_over_mountains: (see description of each parts in [Project Conventions](#project-conventions) section). The filename in this case will be project name or code in short form (like `42design`).

   > **Note.** Please, don't specify year or authors' surnames in filename, because it already stated in file path.

   In this optint all filenames will start with project name in short form. And only by file type reader can detect content of which file belongs to project. Filenames will looks like:

   * For report – `42design.docx`.
   * Presentation – `42design.pdf`.
   * `42design.csv` for dataset.
   
   > **Note**. This option not the best one, when most of your files have same file type (pdf, for example). In thin case use unique filenames option (see below).

2. Using unique file names for specific part of your project. In this case some special requirement applied.

   * Report should be literally named `report`.
   * Dataset: `dataset` or `data`.
   * The same for presentation.
   * All variants of script (original one and output or compiled one) should have the same name (`script.Rmd`, `script.html`).

### Uploading your project

This section guides you through submitting an project for publication to repository by suggested method: `pull request`.

Before making the right folder structore make a fork of repository, after find folder `project/year`, place your files in right places. Path of dataset may looks like `project/2017/Petrov, Sidorov/42design.csv` or `project/2017/Petrov, Sidorov/datset.csv`. After making all preparation, starting the pull request.

#### Pull Request

* Fill in the required template
* Do not include issue numbers in the PR title
* Include screenshots and animated GIFs in your pull request whenever possible.

##### Pull Request Labels

|     Label name     |                                       Description                                        |
| ------------------ | ---------------------------------------------------------------------------------------- |
| `work-in-progress` | Pull requests which are still being worked on, more changes will follow.                 |
| `needs-review`     | Pull requests which need code review, and approval.   |
| `under-review`     | Pull requests being reviewed.                           |

## Credits

Originated from [Atom contribution guide](https://github.com/atom/atom/blob/master/CONTRIBUTING.md).