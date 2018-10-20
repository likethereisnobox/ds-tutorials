# Set up and environment to work with Atom + Hydrogen + Conda Environments
After being a **Sublime Text** user for many years I decided to give **Atom** a go and I have been loving it so far.

For DS work in particular, I have been using the **Hydrogen** package, which lets you execute pieces of code and see the output within the editor. This is similar to Jupyter notebooks, which I think are great for storytelling and data exploration. However, when I am getting closer to turning my code into a working library I prefer this (Atom + Hydrogen) combo.

I am also a big fan of **Conda enviroments**, so here I will tell you my formula for combining these three tools. If you have a better way please let me know, I would love to know about it.

I use macOS, but these instructions should be similar for UNIX-like systems.

## Install Atom
- Just download from their [website](https://atom.io/)
- Unzip package and move to your Applications folder

## Install Hydrogen
- Hydrogen is an [Atom Package](https://flight-manual.atom.io/using-atom/sections/atom-packages/)
- There are two ways of installing packages:
    - Using the commandline: `apm install hydrogen`
    - Using the editor's preferences (Atom > Preferences > Install > Search for Hydrogen > hit the Install button)
- For more details follow the instructions on their [installation instructions](https://nteract.gitbooks.io/hydrogen/docs/Installation.html)

## Install Conda
- Download the Anaconda or Miniconda installation package [here](https://conda.io/docs/user-guide/install/macos.html#installing-on-macos) and follow the instructions

## Create a Conda enviroment
- Create a conda enviroment by doing

`conda create -n ENV_NAME [--file REQUIREMENTS_FILE] [python=<version>]`

- Activate your enviroment

`source activate ENV_NAME`

## Install IPython Kernel using Conda
- `conda install ipykernel`

## Create a Kernel corresponding to your conda enviroment
- `python -m ipykernel install --user --name KERNEL_NAME --display-name DISPLAY_NAME`

## For example:
```console
conda create -n awesome_project --file environment.yml python=3.7
source activate awesome_project
conda install ipykernel
python -m ipykernel install --user --name awesome_project --display-name "awesome project kernel"
```

When you execute code on Atom using Hydrogen for the first time during a session, it will display the following widget to select the kernel you would like to use to execute your code:
![Alternative Kernels Image](https://github.com/likethereisnobox/ds-tutorials/blob/master/img/multiple_kernels.png "Alternative kernels selection")

# You should be good to go!
