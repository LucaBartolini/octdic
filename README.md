# Digital Image Correlation project: setup

## Cloning the Repository 
Very first thing: create a folder on your HD that will keep **all** the stuff relevant to the project. We will call it *DIC_project*.

We will copy the remote (online) repository that I created for `OCT_lib` into the local one (your *DIC_project*).

Using the `Git` software, you could do it automatically and also make sure the repository is kept up-to-date. But for now, it is sufficient to copy the folder on your HD:
- go to [OCT_lib](https://github.com/LucaBartolini/OCT)
- on the right, there's a `Clone or Download` green button
- click on it, then on `Download Zip`
- unzip those contents in your *DIC_project*

Your project folder should now look like:
```
DIC_project
│   
└─── OCT_lib
```

## Managing Environments
1) **Let's make sure that Anaconda is properly installed**
Run the Anaconda Prompt (on Win10: `Windows` key, type `anaconda` and the executable  `Anaconda Prompt (Anaconda3)` should be automatically selected. Press `Enter`  to open it.


2) In the future, You'll end up having more projects, and some of them will have conflicting libraries requirements. A simple solution to that problem is creating **environments**: "enclosed spaces" (in practice it's a folder on your HD). The python interpreter will only see the libraries of the _active_ environment. We'll see what that means in a short while

3) Anaconda, among other things, does exactly that: it's an _environment manager_.

4) To create a new environment, type 

    `conda create -n dic_test`

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
