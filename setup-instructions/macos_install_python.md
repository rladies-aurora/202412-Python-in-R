### Table of Contents:

- [Bash shell](#bash-shell)
- [Python, Conda, and VSCode](#python-conda-and-vscode)
- [R, XQuartz and RStudio](#r-xquartz-and-rstudio)

## Bash shell

Apple recently changed the Mac default shell in the Terminal to Zsh, however, we aim to teach with the same shell across all three operating systems we support, which is the Bash shell. Thus, we ask that you change the default shell in your Terminal to Bash by opening the Terminal ([how to video](https://youtu.be/5AJbWEWwnbY)) and typing:

```
chsh -s /bin/bash
```

You will have to quit all instances of open Terminals and then restart the Terminal for this to take effect.

## Python, Conda, and VSCode

We will be using Python for this demo, and `conda` as our Python package manager as well as VSCode for initial setups. 

**To install VSCode [click here](https://code.visualstudio.com/download)**

**To install Python and the `conda` package manager**, we will use the [Miniconda platform (read more here)](https://docs.conda.io/en/latest/miniconda.html). The latest version of Miniconda for **MacOSX (64-bit)** can be downloaded directly from [this link](https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.pkg).

> **Note:** Miniconda now supports Python **3.11** (or the latest stable version). Ensure compatibility with your project before installation.

After installation, restart the terminal. If the installation was successful, you will see `(base)` prepending to your prompt string. To confirm that `conda` is working, you can ask it which version was installed:
```
conda --version
```
which should return something like this:

```
conda 4.8.2
```

> Note: If you see `zsh: command not found: conda`, see the section on [Bash](#bash-shell){:target="_self"} above to set your default Terminal shell to Bash as opposed to Zsh.

Next, type the following to ask for the version of Python:
```
python --version
```
which should return something like this:

```
Python 3.9.17
```

> Note: If instead you see `Python 2.7.X` you installed the wrong version. Uninstall the Miniconda you just installed (which usually lives in the `/opt` directory), and try the installation again, selecting **Python 3.9**.

## Essential Python packages

`conda` installs Python packages from different online repositories which are called "channels".
A package needs to go through thorough testing before it is included in the default channel,
which is good for stability,
but also means that new versions will be delayed and fewer packages are available overall.
There is a community-driven effort called the [conda-forge (read more here)](https://conda-forge.org/),
which provides more up to date packages
To enable us to access the most up to date version of the Python packages we are going to use,
we will add the more up to date  channel,
To add the conda-forge channel by typing the following in the terminal:


```
conda config --add channels conda-forge

```

To install packages individually, we can now use the following command: `conda install <package-name>`. Let's install the key packages needed for the start of our program:

```
conda install \
 numpy=1.* \
 pandas=1.* 
```

`conda` will show you the packages that will be downloaded,
and you can press enter to proceed with the installation.
If you want to answer `yes` by default and skip this confirmation step,
you can replace `conda install` with `conda install -y`.

## R, XQuartz and RStudio

R is another programming language that we will be using a lot in the MDS program. We will use R both in Jupyter notebooks and in RStudio.

### R

Go to [https://cran.r-project.org/bin/macosx/](https://cran.r-project.org/bin/macosx/) and download the latest version of R for Mac (Should look something like this: R-3.6.1.pkg). Open the file and follow the installer instructions.

After installation, in Terminal type the following to ask for the version:
```
R --version
```

You should see something like this if you were successful:

```
R version 4.0.0 (2020-04-24) -- "Arbor Day"
Copyright (C) 2020 The R Foundation for Statistical Computing
Platform: x86_64-apple-darwin17.0 (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
https://www.gnu.org/licenses/.
```

> Note: Although it is possible to install R through conda, we highly recommend not doing so. In case you have already installed R using conda you can remove it by executing `conda uninstall r-base`.

### XQuartz

Some R packages rely on the dependency XQuartz which no longer ships with the Mac OS, thus we need to install it separately. Download it from here: [https://www.xquartz.org/](https://www.xquartz.org/) and follow the installation instructions.

### RStudio

Download the macOS Desktop version of RStudio Preview from [https://rstudio.com/products/rstudio/download/preview/](https://rstudio.com/products/rstudio/download/preview/). Open the file and follow the installer instructions.


### {tidyverse} R packages

Next, install the key R packages needed for the start of MDS program,
by opening up RStudio and
typing the following into the R console inside RStudio:

```
install.packages('tidyverse', 'rmarkdown', 'usethis')
```

> Note: we will install reticulate together during the demo.
