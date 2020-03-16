# Digital Image Correlation project: setup

## Table of Contents

  - [Table of Contents](#table-of-contents)
  - [Pre-requirements:](#pre-requirements)
  - [Cloning the Repository](#cloning-the-repository)
  - [Managing Environments](#managing-environments)
  - [Setting up the environments and installing basic packages](#setting-up-the-environments-and-installing-basic-packages)
    - [How to make sure python in installed](#how-to-make-sure-python-in-installed)
    - [How to make sure that jupyter is working](#how-to-make-sure-that-jupyter-is-working)
  - [Installing all the files for OCT_lib](#installing-all-the-files-for-octlib)
  - [Running the examples](#running-the-examples)


## Pre-requirements:
- Navigate folders from the `command prompt`: it's enough to know `cd` usage:
  - `cd`  to read the current folder
  - `cd ..`  to move one folder up
  - `cd [relative or absolute path]` to change the current path to that folder
  - Know you can use `tab` to autocomplete
  - Know you can use `UP arrow` to recall last commands
  

## Cloning the Repository 
Very first thing: create a folder on your HD that will keep **all** the stuff relevant to the project. We will call it *DIC_project*.

We will copy the remote (online) repository that I created for `OCT_lib` into the local one (your *DIC_project*).

Using the `Git` software, you could do it automatically and also make sure the repository is kept up-to-date. But for now, it is sufficient to copy the folder on your HD:
- go to [OCT_lib](https://github.com/LucaBartolini/OCT)
- on the right, there's a `Clone or Download` green button
- click on it, then on `Download Zip`
- unzip the folder inside the zip file into your *DIC_project*

Your project folder should now look like:
```
DIC_project
│   
└─── OCT-master
```

## Managing Environments
1) **Let's make sure that Anaconda is properly installed**
Run the Anaconda Prompt (on Win10: `Windows` key, type `anaconda` and the executable  `Anaconda Prompt (Anaconda3)` should be automatically selected. Press `Enter`  to open it.


2) In the future, You'll end up having more projects, and some of them will have conflicting libraries requirements. A simple solution to that problem is creating **environments**: "enclosed spaces" (in practice it's a folder on your HD). The python interpreter will only see the libraries of the _active_ environment. We'll see what that means in a short while

3) Anaconda, among other things, does exactly that: it's an _environment manager_.

4) To create a new environment, type 

    `conda create -n dic_test python=3.7`

    We are fixing the python version to 3.7 because of compatibility. That restriction might be eased in the future.

5) To make sure that the creation was successful, we can list all the available environments, typing:
    
    `conda info --envs`

    you should see `base`, the default environment, and the newly created one.

6) Now we _activate_ that environment, typing:

    `conda activate dic_test`

    Remember, once you close the prompt and open it again, it reverts to the default environment, and you will have to activate your intended env again. 

7) We can see the environment folder with:

    `where python` (on Windows)

## Setting up the environments and installing basic packages
The are two basic commands to install packages, and you will have to use both (sometimes one work, but the other doesn't, or viceversa). If you don't know which one to use, just try, it's hard to break anything, and if you do, you simply recreate the environment :)

The Anaconda packet manager is invoked with:

`conda install [packet name]`

The `python` distribution also has its own packet manager, that you probably already know:

`pip install [packet name]`

Let's start (but first **make sure** that the correct environment is activated), then:

1) `conda install python`
2) `conda install jupyter`
3) `conda install -c conda-forge jupyter_contrib_nbextensions` this will add useful extensions (plug-ins) to jupyter notebook
4) `pip install jupyterthemes` this is another plugin that will allow you to use dark themes
   - after that, to set a nice dark theme: `jt -t onedork -cellw 1080 -T`
   - if you wanna play around with the themes, check out it's [GitHub repository](https://github.com/dunovank/jupyter-themes). 

### How to make sure python in installed
Simply type:

`python`

If that doesn't work, you may have to add your anaconda path to the system environment variables. It's quite simply, and there are a lot of online tutorials that explain it better than I could. If it pops up during our Skype session, we'll do it together.

### How to make sure that jupyter is working
- Make sure the relevant environment (last time I say it): `conda activate dic_test`
- Run jupyter: `jupyter notebook`
- The command will start a local server, living within your command prompt, and your browser connect to that server and provide you with a nice interface to run python code and much more. 
- Later, you will set up your jupyter extensions in [here (jupyter must be running in your prompt)](http://localhost:8888/tree#nbextensions_configurator)

## Installing all the files for OCT_lib
From within the Anaconda prompt, navigate to the `OCT_lib` folder; the command will be something like:

`cd "some_path\DIC_project\OCT-master"` 

When you are inside that folder, with the correct environment activated,  you can install all the required packages (libraries) by typing:

`pip install -r requirements.txt`

the package manager `pip` will install each necessary library. This command is the bottleneck of the process, and doesn not work smoothly on every machine. We'll have to work through it somehow.

These commands might come in handy:
- `conda install -c menpo opencv=3`
-  


## Running the examples
At the end, the examples from OCT_lib should be running fine.
From the prompt:

- `cd` to `OCT-master`
- run `jupyter notebook`
- open the example folder in the Jupyter navigator (under tab `Files` in http://localhost:8888/tree)
- See if the first cell works. If so, the imports are successful, which means you have all the libraries correctly installed. If it doesn't, read the error and work on the installs based on what the error says. 
