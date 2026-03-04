# Title

## Purpose

## Prerequisites

### Required Software
There are a few programs that we will need to install ...

| Tool | What It Is | What It Does |
|------|------------|--------------|
| **Python** | A programming language | Lets developers write instructions that a computer can run, It is used to build tools, automate tasks, analyse data, and more |
| **Git** | A version control system | Tracks every change ever made to a project's code, so a team can see the full history, undo mistakes, and work on the same files without overwriting each other |
| **pip** | A package installer for Python | Downloads and installs ready-made code libraries so developers don't have to build everything from scratch, it works like an appstore for python |  
(Bias towards including tables - Etter)

Run the following command in your Terminal application
`sudo apt -y install git python3-python python3-pip`  
(Use inline styles to offset important text - Etter)

### A GitHub Account
If you do not already have one, create a free account at [github.com](https://github.com). This is where your project will be stored and where the live website will be hosted.  
(Link liberally, don't duplicate - Etter)

### Setting Up Github SSH Keys
Unlike many programs you are already framiliar with GitHub no longers supports logging in with a user name and password, what you have to do instead is create a Git SSH Key  
You can learn how to do that [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux)  
(Link liberally, don't duplicate - Etter)

#### Step 1 – Install the Deployment Helper
This is a small tool that sends your finished website up to the internet. Run the following command in your terminal to intall it

```
python -m pip install ghp-import
```

#### Step 2 – Install Pelican
Pelican is the tool that actually builds your website. In your Terminal run:

```
python -m pip install pelican
```

#### Step 3 – Create a New Repository
A "repository" is just an online folder where your website files will live. Github is where our repository is hosted

1. Once logged in to GitHub, click the **+** icon in the top-right corner
2. Select **New repository**
3. Name it `marvinmclaren.github.io` 
4. Leave it set to **Public**
5. Click **Create repository**


#### Step 4 – Download Your Repository to Your Computer
This links your online folder to a folder on your own machine. In your Terminal run:

```
git clone https://github.com/username/marvinmclaren.github.io
```

> **Note:** Replace `username` with the GitHub username you chose in Step 5.

Then navigate into that folder by running:

```
cd marvinmclaren.github.io
```

#### Step 5 – Run the Website Setup Wizard
Pelican includes a setup assistant that asks you a few simple questions. Run:

```
pelican-quickstart
```

When it asks for a **URL prefix**, enter:

```
https://marvinmclaren.github.io/website
```

You can press **Enter** to accept the defaults for all other questions.

#### Step 6 – Save Your Files to GitHub
Think of this like hitting "Save" and then uploading to the cloud. Run these two commands:

```
git add .
git commit -am "First commit"
git push origin main
```

#### Step 7 – Build and Publish Your Website
These three commands generate the finished website and send it live:

```
pelican content -s publishconf.py
ghp-import output -b pages
git push origin gh-pages
```

#### Step 8 – Tell GitHub to Serve Your Website
This is a one-time setting you only need to configure once:

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. In the left sidebar, click **Pages**
4. Under **Branch**, select `pages` and click **Save**

#### Step 9 Viewing Your Live Website

After a minute or two, your website will be live at:

```
https://marvinmclaren.github.io
```

Paste that address into your browser to see it!

> !Making Updates in the Future
* Whenever you want to update your website, simply repeat **Step 7**. Your changes will be live within a couple of minutes.

## Futher Resources

## FAQ

## Credits
