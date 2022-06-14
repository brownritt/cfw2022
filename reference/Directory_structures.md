# Directory structures

There are many ways to set up a project directory structure, and no one way will work well in all settings. Some broad rules of thumb are to keep code and data separate, and to distinguish "raw" data (e.g. coming directly from an experimental system) from "pre-prcoessed" data, as described in lecture.

One should also provide a distinct location for analysis outputs, typically figures and/or numerical tables; the choice of output organization is often subtle, as one may want to keep many different versions of analyses, for example with differing parameters.

Tools like [cookiecutter](https://github.com/cookiecutter/cookiecutter), which build project directory structures from templates, are useful when projects are especially complex or when you will be making many similar projects. However, it's usually enough to manually put a few key directories in place initially, and adjust as need.

We recommend setting up the skeleton first, before `git` initialization.

An example minimal structure for a data science project could be
```
project_name/
|- README.md
|- data/
|  |- raw/
|  \- derived/
|- code/
\- figures/
```

One often adds an environment file to the top directory to keep track of any package installations, and a `.gitignore` that excludes (at least) the data and figure directories.

*Note*: `git` can be very inefficient with large binary (non-text) data files. Usually one should include only code and small files in the commits. There are other systems for preserving and tracking large data files. If the data is particularly complicated or large, it may be kept somewhere other than in the project directory, at the expense of an easliy shared single directory that contains all project information.

If one is developing general software instead of doing data analysis the project structure changes accordingly. There would not be `data` or `figures` directories, and there might be other directories like `assets` (e.g. used to store images, sound files, or other media used in an app) or `bin` ("binary", used for executable files).

There are many other naming conventions. For example, for historical reasons the `code` directory is often named `src`, an abbreviation of "source", which is short for "source code." Configuration files are often in an `etc` directory, and some people separate `scripts`, code that is meant to be run from a shell as utilities, from the "main" code in `src`.

As usual, a good approach is to start simple, using whatever works for you and your collaborators, and then learn from and adjust to your experience over time.
