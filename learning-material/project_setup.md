# Starting a new image analysis project

If you have set up Python and installed Napari and Jupyter lab, you can start prototyping something for your image analysis project.

One of the first challenges you'll face is deciding how to organize the structure of your project. A simple way to get started would be as outlined below.

- Create a new folder for your project.
- Create a sub-folder called `data` in which you're going to keep your image(s). Move your data there.
- Create a Jupyter notebook file with an extension `.ipynb` for your analysis.

```
my_project/
    ├── data/
        ├── image.tif
    analysis.ipynb
```

```{tip}
By keeping data close to your code, it's easier to refer to it via *relative paths* in your code.
```

Then, open your terminal and follow the steps below.

1. From the command-line, navigate to the folder you just created using `cd`. For example:
```
cd ~/Desktop/my_project/
```
1. Activate your `Python environment`.
```
conda activate napari-env
```
1. Start the `Jupyter Lab` application.
```
jupyter lab
```

Jupyter Lab will open in a web browser window. There, you can open your analysis notebook and start working on it.

A good start would be to add a title for your analysis in a `Markdown` cell, import a few libraries, and load an image from your `data` subfolder.

```{code} python
import skimage.io

image = skimage.io.imread('data/image.tif')

print(f'Loaded image in an array of shape: {image.shape}.')
print(f'Intensity range: [{image.min()} - {image.max()}]')
```

In the next cell, create a Napari viewer and open your image in it.

```
import napari

viewer = napari.view_image(image)
```

If you run these two cells, Napari should open in a separate window. You should be able to see your image in the viewer. From here, you're ready to start developing an image analysis pipeline based on your [project objectives](https://docs.google.com/document/d/1NUFKOpXunjs9hOxmn5RvLNrfcF0DhXfgoVGIL3-eXiA/).

## Going further

To complete the structure of your project, you can add, for example

- a `README.md` file to document your project.
- a `requirements.txt` file to specify the Python dependencies for your project.
- a `LICENSE` file to specify your project's license.

Learn more about good practices coding projects by reading EPFL ENAC-IT's [Code Publishing Cheat Sheet](https://www.epfl.ch/schools/enac/wp-content/uploads/2022/06/ENAC-IT4R_Code_Publishing_Cheat_Sheet.pdf).

In addition, you might consider tracking changes to your project using [`git`](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) for version control and hosting your project on a platform such as [GitHub](https://github.com/) or [GitLab](https://gitlab.com/). You can keep your project *private* or make it *public* to share it with others.
