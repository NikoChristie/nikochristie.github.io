# Markdown & Static Websites with Pelican & Github

## Purpose

The purpose of this README is to teach Marvin McLaren how to host their own static website on GitHub with Pelican

## Prerequisites

### Required Software
There are a few programs that we will need to install ...

| Tool | What It Is | What It Does |
|------|------------|--------------|
| **Python** | A programming language | Lets developers write instructions that a computer can run, It is used to build tools, automate tasks, analyze data, and more |
| **Git** | A version control system | Tracks every change ever made to a project's code, so a team can see the full history, undo mistakes, and work on the same files without overwriting each other |
| **pip** | A package installer for Python | Downloads and installs code libraries so developers don't have to build everything from scratch, it works like an app store for python |  
  
(Bias towards including tables - Etter)

Run the following command in your Terminal application  
```
sudo apt -y install git python3-python python3-pip
```  
(Use inline styles to offset important text - Etter)

### A GitHub Account
If you do not already have one, create a free account at [github.com](https://github.com). This is where your project will be stored and where the live website will be hosted.  
(Link liberally, don't duplicate - Etter)

### Setting Up Github SSH Keys
Unlike many programs you are already familiar with GitHub no longer supports logging in with a user name and password, what you have to do instead is create a Git SSH Key. You can learn how to do that [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=linux)  
(Link liberally, don't duplicate - Etter)

## Instructions

### Step 1 – Install the Deployment Helper
This is a small tool that sends your finished website up to the internet. Run the following command in your terminal to install it

```
python -m pip install ghp-import
```  
(Use inline styles to offset important text - Etter)


### Step 2 – Install Pelican
Pelican is the tool that actually builds your website. In your Terminal run:

```
python -m pip install pelican
```  
(Use inline styles to offset important text - Etter)  

### Step 3 – Create a New Repository
A "repository" is just an online folder where your website files will live. Github is where our repository is hosted

1. Once logged in to GitHub, click the **+** icon in the top-right corner
2. Select **New repository**
3. Name it `marvinmclaren.github.io` 
4. Leave it set to **Public**
5. Click **Create repository**  
(Ordered List - Etter)


### Step 4 – Download Your Repository to Your Computer
This links your online folder to a folder on your own machine. In your Terminal run:

```
git clone https://github.com/username/marvinmclaren.github.io
```

> **Note:** Replace `username` with the GitHub username

Then navigate into that folder by running:

```
cd marvinmclaren.github.io
```  
(Use inline styles to offset important text - Etter)  

### Step 5 – Run the Website Setup Wizard
Pelican includes a setup assistant that asks you a few simple questions. Run:

```
pelican-quickstart
```

Answer the questions with the following answer  
![Pelican Quick Start Answers](https://github.com/NikoChristie/nikochristie.github.io/blob/master/Images/PelicanQuickStart.png)

### Step 6 - Create Your New Post

1. Create a new file in the `content` directory  
2. Call the file whatever you want, it should end in the `.md` file extension so the system knows that it is a markdown  
3. At the beginning of the file you **must** include the following information
```
Tile: <Your Title>
Date: YYYY-MM-DD HH:MM
Category: <Your Category>
```
4. Now you can put your new Markdown skill to work write about whatever you want and then save the file

You can press **Enter** to accept the defaults for all other questions.

### Step 7 – Save Your Files to GitHub
Think of this like hitting "Save" and then uploading to the cloud. Run these two commands:

```
git add .
git commit -am "First commit"
git push origin main
```  
(Use inline styles to offset important text - Etter)  


### Step 8 – Build and Publish Your Website
These three commands generate the finished website and send it live:

```
pelican content -s publishconf.py # Builds your website
ghp-import output -b pages        # Packages the website for upload
git push origin gh-pages          # Publishes the website live
```

Here is a brief explanation of what each command does

1. **Builds your website**  
   Think of this like hitting "Print" it takes all your raw content and converts it into a polished website ready to be seen by visitors.
2. **Packages the website for upload**  
   This bundles your freshly built website into a format that GitHub can understand and serve to the public
3. **Publishes the website live**  
   This is the "Send" button it uploads your packaged website to GitHub, making it instantly visible to anyone with your website's address.  
(Ordered list - Etter)


### Step 9 – Tell GitHub to Serve Your Website
This is a one-time setting you only need to configure once:

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. In the left sidebar, click **Pages**
4. Under **Branch**, select `pages` and click **Save**  
(Ordered list - Etter)

### Step 10 Viewing Your Live Website

After a minute or two, your website will be live at:

```
https://marvinmclaren.github.io
```  
(Use inline styles to offset important text - Etter)  


Paste that address into your browser to see it!

> [!Important]
> Whenever you want to update your website, simply repeat **Steps 7 & 8**. Your changes will be live within a couple of minutes.

## Futher Resources

[Official Github Markdown Guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
GitHub uses a flavor of Markdown called GitHub Flavored Markdown (GFM), which extends standard Markdown with extras like task lists, tables, syntax-highlighted code blocks, and @mentions. 

[Learn More About How To Use Git](https://learngitbranching.js.org/)
Learn Git Branching is an interactive, visual tool that teaches you how Git works through hands-on challenges directly in the browser. 

[Learn About The Python Programming Language](https://en.wikipedia.org/wiki/Python_(programming_language))
Python is a high-level, general-purpose programming language it is one most popular languages in the world. It is the programming language behind Pelican.

[Learn About The PIP Package Manager](https://en.wikipedia.org/wiki/Pip_(package_manager))
pip (short for "Pip Installs Packages") is the standard package manager for Python, allowing developers to easily install and manage third-party libraries.

## FAQ

### Why is Markdown Better Than Writing Raw HTML?

Markdown isn't necessarily better than HTML, like most things it depends on your use case. Take a look at the comparison below

#### HTML
```
<h1>Title</h1>
<p>This is some text, <strong>This is some bold text</strong> . </p>
```

#### Markdown
```
# Title
This is some text, **this is some bold text**
```

Both will give you more or less the same output, markdown as you can see is much more terse  
However HTML is *much* more powerful that Markdown. It excels at custom styling and fine grained control  
For the average use case Markdown usually does a good enough job  

### I Changed The Markdown Version Of My Resume, So Why Don't I See The Changes When I Refresh The Website In My Browser?

Updating a markdown version on your computer won't immediately change it on GitHub and in turn on your website  
To have it update your server you must **repeat steps 7 & 8**, changes can take up to two minutes to become available on your website

## Credits

Arthur McMullen  
Bradley Barrientos

