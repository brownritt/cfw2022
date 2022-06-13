# Installation notes
Part of Computational Fluency Workshop 2022 at Brown University. Some notes on installation of various tools. *These are not comprehensive instructions*, and are intended only to help point to useful sources, and provide a few pointers.

## Git

`git` is by far the most dominant version control system. 

General information can be found at [https://git-scm.com](https://git-scm.com), including installation instructions for different OS and documentation. Before attempting to install, check if you already have it, for example on Mac or Linux by typing in a terminal:
```shell
which git
```

For **Mac** installation we suggest using the version that comes with `Xcode`. You have to first install `Xcode` from the App Store. This can take a long time; `Xcode` is a massive package with a lot of tools you would need only if you start developing for Apple products. However, this is the "native" approach, and will provide updates, etc. If you would rather have a leaner install of just `git`, see the SCM link above, or the GUI options below.

`git` is both the underlying version control system and a command line tool. Various third parties offer graphical interfaces, for example
[GitHub Desktop](https://desktop.github.com). This may be the best option for **Windows**.

Most IDEs support some kind of `git` integration, but they can take some work to set up properly. Once your own workflow starts to stabilize you can revisit your toolkit and personalize as you see fit.

[GitHub](https://git.com) is the biggest online platform for sharing `git` repositories, but it is not the only one, and it is not necessary to use `git` (there is no formal relationship between the tool itself and the online platforms). However, you will likely want to make an account there in order to be able to "push" code from your computer and contribute to projects.

## Python

We suggest the [Anaconda distribution](https://www.anaconda.com/products/distribution) as a good starting place for learning to use python for data science. There are leaner ways to install python, but for most data scientists the convenience is more important than the size.

Installing Anaconda will also install the general tool `conda`, which handles package management and virtual environments.

Note that Anaconda Navigator is an app that comes with the distribution, but that is not necessary to use python. You may or may not prefer the GUI interface for new projects.

