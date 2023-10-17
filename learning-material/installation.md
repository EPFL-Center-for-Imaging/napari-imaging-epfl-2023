# Python setup & Napari installation

```{note}
You can also find the official Napari installation instructions [here](https://napari.org/stable/tutorials/fundamentals/installation.html#installation).
```

## Install Python using `conda`

Napari is a Python package. Therefore, to install it, you must first install Python. If you haven't yet installed Python, Anaconda, or Miniconda on your machine, we recommend you install `Miniconda` which is based on the [conda package manager](https://docs.conda.io/en/latest/). Click on the link below to download the installer:

**Miniconda**: https://docs.conda.io/en/latest/miniconda.html

Once you have downloaded the installer, run it to install Python.

`````{tab-set}
```{tab-item} Windows
1. Run the executable file you just downloaded (`Miniforge3-Windows-x86_64.exe`) and follow the instructions.
2. Launch the *Anaconda Prompt* terminal from the start menu.
```
````{tab-item} Mac / Linux
1. Open your Terminal (you can search for it in spotlight - `cmd` + `space`)
2. Navigate to the folder you downloaded the installer to using `cd`. For example:

```bash
cd ~/Downloads
```

1. Execute the installer with the command below. You can use your arrow keys to scroll up and down to read it/agree to it.

```bash
bash Miniforge3-MacOSX-x86_64.sh -b
```

2. To verify that your installation worked, close your terminal window and open a new one. You should see `(base)` to the left of your prompt.
3. Finally, initialize miniforge with the command below. This makes sure that your terminal is set up correctly for your Python installation.

```bash
conda init
```
````
`````

```{admonition} Verify your installation
:class: tip
Verify that you have **conda** installed by typing `conda -V` in your terminal. This should print out a version number.
```

## Set up your Python environment

We will create a Python virtual environment that you can use for this workshop. Using a virtual environment is a good practice; it lets you isolate the packages and dependencies that you are using for a specific project, without them interfering with other Python projects you may be working on.

Type the following commands in your terminal to create a virtual environment (named `napari-env`) using `conda`:

```bash
conda create -n napari-env python=3.9
```

The `-n` parameter specifies the name of the virtual environment (here, *napari-env*). We also specify the Python version to be 3.9. Python is constantly evolving and new versions are regularly released. At the time of writing, modern versions include 3.8 to 3.11.

```{tip}
You can check which virtual environments are available on your machine by typing `conda env list`.
```

Next, let’s install a few Python packages into your *napari-env* virtual environment. To do that, you first have to *activate* the environment.

```bash
conda activate napari-env
```

If you successfully activated the environment, you should see `(napari-env)` to the left of your command prompt.

Install [Napari](https://napari.org/stable/) using the [pip](https://pip.pypa.io/en/stable/) package manager by typing the following commands:

```bash
pip install "napari[all]"
```

Install [Jupyter lab](https://jupyter.org/):

```bash
pip install jupyterlab
```

## Check your installation

With your virtual environment activated,

- type `napari` in your terminal. The Napari viewer should open **in a separate window**.
- type `jupyter lab` in your terminal. This should start the Jupyter lab application in your web browser. To stop Jupyter lab, close the web browser and press `Ctrl+C` in your terminal window.

You’re done with the Python setup. Congratulations! 🙌