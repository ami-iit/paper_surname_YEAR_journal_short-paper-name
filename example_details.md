# Paper Repositories Example 

This repository contain an example of the repository associated to a paper published by members of [Artificial Mechanical Intelligence research line at the Italian Institute of Technology](https://ami.iit.it/).

In the spirit of [Open Science](https://en.wikipedia.org/wiki/Open_science) for each paper this repository is meant to contain all the LaTeX sources, data and software required to 
easily reproduce the results presented in the paper.

## Contents

Each repository paper should contain:
* [`README.md`](README.md): entry point for the paper content, with links to the paper itself, the video description of the paper, the code of the paper and any other related content.
* [`CITATION.cff`](CITATION.cff): metadata necessary for GitHub to generate the "Cite this repository" link, see [GitHub docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-citation-files#other-citation-files) for more info. Note that it is important to use the `preferred-citation` field to ensure that actual doi of the published paper is used for citations.

## How To Create a New Paper Repository

To create a new paper repository, one can start by creating (or asking to create) in the `ami-iit` repository a repository with the name in the format `paper_surname_YEAR_journal_short-paper-name`, and copy in it the files from this example, deleting the `example_details.md` file and inserting the specific data of the paper.

## Licenses

For papers published in the Artificial Mechanical Intelligence, the license that we use are:
* [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) for the actual paper contents,
* [BSD-3-Clause](https://opensource.org/licenses/BSD-3-Clause) for the software and scripts.

However, the preferred license could be different and is tipically selected on a case by case basis.

## Reproducible Installation

In general, it is always a good idea to attach to any experimental results the precise version of the software that you used to obtained those results, for example by running https://github.com/ami-iit/log-installed-software. To ensure that other people are able to run your software, it is also useful in general to compile the installation instructions in a way that is **reproducible**, i.e. install the same version of the software also in the future.

Depending on how you install software, how you implement reproducible installation is different. In the following, we list some examples:

### apt-based installation

If you have some dependencies installed via `apt`, for example:
~~~
sudo apt install python3-opencv
~~~
there is no need to explicitly specify the version of the package you used, as long as clearly document the distribution and its version (for example, Ubuntu 20.04) that you used to run the software. Even better, you can also prepare a Docker image that runs that distribution to simplify the use of the software from people in the future that will use more recent distributions.

### conda-based installation

If you are install some dependencies via `mamba`, for example:
~~~
mamba install opencv
~~~
the easiest way to make this installation reproducible is to specify the version of opencv to install, i.e.:
~~~
mamba install opencv==4.7.0
~~~

If you are using an [environment.yml file](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-file-manually), you should pin the version in the environment file, for example:

~~~
name: paperenv
channels:
  - conda-forge
dependencies:
  - opencv==4.7.0
~~~

### pip-based installation

If you are install some dependencies via `pip`, for example:
~~~
pip install opencv
~~~
the easiest way to make this installation reproducible is to specify the version of opencv to install, i.e.:
~~~
pip install opencv==4.7.0
~~~

If you installing your dependencies via a `requirements.txt` or `setup.cfg`, you can pin the version even there.


## FAQs

### It is necessary to commit all the software that was developed for a given research in the paper repository?

No, the paper repo is just meant to host the code strictly related to the results presented in the paper.

If you developed some software that is already in reusable form (such as a Python package, a C++/CMake package, a MATLAB library) that software
should be published in a different repository, and used as any other dependency. In particular, as any other dependency the installation section of the README
should document the **exact version of the dependency used in the paper**, to avoid that in the future users get different results due to a different version of some dependencies, including your own reusable code. 

The basic idea is that reusable code is meant to change over time, get new features, adapted to work on more modern operating systems, while 
the code in a paper repository is meant to **reproduce exactly the results presented in the associated paper**.

## Example of Paper Repositories from the past

Note, older repos may not be respect all guidelines or indication that are indicated in this example.

### 2021 
* [`romualdi-2021-ral-soft_terrain_walking`](https://github.com/ami-iit/romualdi-2021-ral-soft_terrain_walking)
* [`tirupachuri-2021-access-estimation_payload_stresses`](https://github.com/ami-iit/tirupachuri-2021-access-estimation_payload_stresses)
