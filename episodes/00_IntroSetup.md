---
title: "Introduction and Setup"
teaching: 10 # teaching time in minutes
exercises: 0 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- What can I expect from this course?
- What are the prerequisites?
- What is the technical setup?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Manage expectations for this course
- Identify prerequisites for this course
- Everyone has a working environment for this course

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

This course introduces the eLabFTW API and how to use it. It is designed for researchers who want to interact with their eLabFTW instance programmatically. As such, you should be familiar with using eLabFTW through it's user interface (UI).

Since this course is supposed to reach as many researchers as possible, it does contain some very basic concepts on APIs, Python, and Jupyter Notebooks. Bear with us here if you are already familiar with these concepts. We will also code some short example scripts that act upon the data so we can work through a mildly realistic sceanario.

<!--Note on where content can be found (link)/Intro slides-->

## Notes and Resources

We have joint notepad for this course. Feel free to job things down: <!-- link to notepad -->

## Setup

This course borrows from the concepts of [The Carpentries](https://carpentries.org/). Thus, it contains a lot of live coding and exercises–it's hands on! That means, you will need some kind of working environment.

If you use Jupyter Notebooks on your computer and already feel comfortable using things like a terminal there, feel free to stay local. If you cannot or do not wish to install anything, you can use a JupyterHub instance. We have outlined two options below.

### [RWTH JupyterHub](https://jupyter.rwth-aachen.de/hub/) (requires RWTH Account)

1. Head to <https://jupyter.rwth-aachen.de/hub/> and log in with your RWTH account. 
2. Then Select the **Python 3.13** profile. 

![Screenshot of the RWTH Jupyter Hub profile selection](img/screenshot_RWTHjupyter_profiles.png)

3. Then Scroll down and click **START**.

![Screenshot of the RWTH Jupyter Hub start button](img/screenshot_RWTHjupyter_start.png)

### [Jupyter4NFDI](https://hub.nfdi-jupyter.de/hub/home)

1. Head to <https://hub.nfdi-jupyter.de/hub/home> and click **Sign In**.
2. Select an **NFDI consortium** or **Guest Access**. Log in accordingly.
3. Give your lab a name and click **start**. The basic settings are sufficient for our course.

Whichever path you chose, you should now see something like this (or whatever your local setup is):

![Screen shot Jupyter Lab](img/screenshot_jupyterLab.png)

### Course Material

::::::::::::::::::::::::::::::: instructor note
live code in jupyter lab from here on out.
::::::::::::::::::::::::::::::::::::::::::::::::

Next, no matter where you are working, you will need to download the course materials. Open a terminal and run the following command (feel free to copy and paste from notepad):

```bash
git clone https://TODO_UPDATEME/rdmIII_elabAPI_researcher.git
```

This gives you the entire course content. Switch to the course learner directory in the file explorer to the left of the screen.

Note: your are more than welcome to download the entire course content. Especially if you are working on Jupyter4NFDI, we encourage you to **download and save your work** before closing the server. You can do this by clicking on the **File** menu and selecting **Download**. This will download a zip file containing all your work. do this by exporting your workspace (in the **File** menu).

### eLabFTW Access

You should have created an account on the eLabFTW demo instance <https://elab.parks.web.gateway.ionos.coscine.dev> and have access to the course team. This will allow you to play around however you please without spamming an official instance.

If not, register to the demo instance and select the team **20261115_FDMIII_API**. Let us know so an admin can grant you access.

## Note on the Carpentries

The Carpentries are a non-profit organization that teaches foundational coding and data literacy skills to researchers. They have a very specific way of teaching and structuring their lessons. We will borrow some of their concepts, but we will not follow their structure to the letter. If you are interested in learning more about the Carpentries, please visit their website: <https://carpentries.org/>. <!-- check if I used any of their content and and give attribution here where necessary-->

