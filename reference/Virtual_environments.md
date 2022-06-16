# Basics of virtual environments
Virtual environments keep track of your codes "dependencies", which is the set of other software needed to run your code. If you send someone else your code without those dependencies, there's a good chance your code won't work on their system.

Rather than send someone a full copy of your operating system (which is close to what a *container* does), it is often enough to list in a very precise way (that is, precise to a computer) what other code their system might need. This is an approximate way to communicate dependencies, and sometimes fails, but has the virtue of being efficient (only a small "environment" needs to be included in your repo) and descriptive (you explicityly describe what you used, rather than send some incomprehensible mess of code).

### Using `conda` for virtual environments

If you have `conda` on your system, you can make a virtual environment with a command like
```
conda create -n fmri_analysis numpy pandas matplotlib
```
This tells `conda` to create a new virtual environment named `fmri_analysis` (that's what the `-n` otpion does), and to include in that environment the packages `numpy`, `pandas`, and `matplotlib`, assuming it can find them at expected locations online. Note `conda` will also install *all packages that those packages depend on*, and `conda` may also need to make changes to other packages already on your system, if the versions do not match. This is a complicated process, which is why most of the time we want to let the package managers sort it out if they can.

If you are currently in a virtual environment, you can make a file that describe the environment with
```
conda env export -f environment.yml
```
This will make a new file `environment.yml` (in the current working directory) that lists all the packages in the current environment. If you send that file to someone else, they can recreate your environment with
```
conda env create -f environment.yml
```
Note the `env` invocation of the "envionrment" module (it is included when creating from an environment file but not when creating from a command line list of packages). This create command does not include a name for the virtual environment; the name is listed inside the `environment.yml` file, and that is the name `conda` will use.

One useful pro-trick is to export a list of just the packages you actually requested, not including all the other packages `conda` installs to satisfy the dependencies:
```
conda env export --from-history -f environment_minimal.yml
```
This will also make a file that can be used with "create", but will list only the packages you explicitly requested. In the above `fmri_analysis` example, the file `environment_minimal.yml` would list just the packages  `numpy`, `pandas`, and `matplotlib`, while the file `environment.yml` would list a bewildering array of many, many packages including detailed version numbers.

We suggest including both types of environment files in your repos. The more explicit version is needed for reproducibility, but if anything goes wrong, the minimal version communicates what you intended to set up.
