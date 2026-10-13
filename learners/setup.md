---
title: Setup
---

:::::::::::::::::::::::::::::::::::::::: callout

We will be in the workshop room 30 minutes prior to the workshop starting. Please come early if you have any issues with this setup!

::::::::::::::::::::::::::::::::::::::::::::::::

## Software Setup

### eLabFTW

We will use a demo instance of eLabFTW. As such, we have created a team for this workshop.

To access the demo instance and team:

1. Head to https://elab.parks.web.gateway.ionos.coscine.dev/register.php
2. Select the team `YYYY-MM-DD_FDMIII_API` (where YYYY-MM-DD is the date of the workshop)
3. Fill in your information
4. Click `Create`

You will have access to this team for 4 weeks after the workshop. Your account will then be deleted.

### Jupyter Lab

This course borrows from the concepts of [The Carpentries](https://carpentries.org/). Thus, it contains a lot of live coding and exercises–it's hands on! That means, you will need some kind of working environment.

Everything is designed so you do not have to download and install anything locally (you can, if you like). We will use an online version of Jupyter Lab for everything we do. If you are an RWTH Aachen member, feel free to use the RWTH's Jupyter Hub. Otherwise, you may use Jupyter4NFDI.

Jupyter Lab is an environment that allows you to code in Python (or Julia, R, ...), interact with a terminal, and so on. It is an easy way to get started – and notably, to teach courses like this.

:::::::::::::::::::::: spoiler

### [RWTH JupyterHub](https://jupyter.rwth-aachen.de/hub/) (requires RWTH Account)

1. Head to https://jupyter.rwth-aachen.de/hub/login and sign in with your credentials
2. Select the `Python 3.13` profile
3. Scroll down and click `START`

Most things appear to remain saved in Jupyter Hub - but I would still recommend downloaded the content after the course if you want to ensure full access to what you did.

::::::::::::::::::::::

:::::::::::::::::::::: spoiler

### [Jupyter4NFDI](https://hub.nfdi-jupyter.de/hub/home)

1. Head to https://hub.nfdi-jupyter.de/hub/login and click `Sign in`
2. Follow the instructions to sign in
3. Accept the acceptable use policy
4. Give your new Jupyter Lab a name. The base configuration should be sufficient.
5. Click 'Start`

Remember to download everything if you want to keep it after the course!

::::::::::::::::::::::

All course material (included a filled-out version of the notebook) will be available after the course via Moodle.

## Datasets

Once Jupyter Lab is running, open a new terminal and run the following command (copy-paste and hit enter):

```bash
#TODO: fix the below by replacing BRANCH, OWNER, REPO, and path/to/folder with the correct values
git clone --depth 1 --filter=blob:none --sparse --branch BRANCH \
  https://github.com/OWNER/REPO.git
cd REPO
git sparse-checkout set path/to/folder
```

This will retrieve the `workshop_data` folder directly.

:::::::::::::::::::::::::::::::::::::::: callout

The `workshop_data` folder is also available via the Moodle room. Here, you may download it and upload it to Jupyter Lab - especially useful in case there are any problems with retrieving it with the instruction above.

::::::::::::::::::::::::::::::::::::::::::::::::
