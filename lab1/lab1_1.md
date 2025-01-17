---
title: "Getting Started"
date: "2024-01-17"
output:
  html_document: 
    theme: spacelab
    toc: true
    toc_float: true
    keep_md: true
---



## Background_Change_anotherChange  
In nearly every field of science, our ability to generate data has exceeded our capacity for analysis. For me, this means that there is the potential for loss to science; many important discoveries may go unnoticed because we are unable to efficiently analyze data.  

The goal for this course is to help get you started learning to manage, transform, and visualize data using the R programming language. You will learn to clearly and neatly organize messy data, transform it in ways that address your questions, and communicate results in a variety of formats. The course is designed for people with **no prior programming experience**. There is a substantial learning curve but, working together, we will make learning R easier, interesting, and fun.  

This class is NOT focused on statistical analysis or interpretation. The goal is to provide you with the tools you need to perform these tasks.  

## First steps  
It is important that you understand the first two weeks of the class can seem slow, tedious, and frustrating. These first steps are like learning a new language; you often won't know what is being said or why. Please be patient and stick with me! I promise that it will get easier.  

## Resources  
Given that R is open source, many resources are available online. We will use a combination of resources in the class, but key items are listed below.  

- [Class Website](https://jmledford3115.github.io/datascibiol/)  
- [Class YouTube](https://www.youtube.com/channel/UCFX-MipGKF9jCEXaP-59BzQ)  
- [R for data science](https://r4ds.had.co.nz/)
- [R cheatsheets](https://posit.co/resources/cheatsheets/)

## UC Davis  
Our campus has a wealth of expertise in data science. Should your interests progress, here are some links. They offer regular workshops and maintain archives. Among the goals of this class is to get you set-up so that you can attend these workshops and learn more!  

- [Davis R Users Group](http://d-rug.github.io/)  
- [Data Science Initiative](http://dsi.ucdavis.edu/)  

## Help!  
When you need help with homework or a class topic, please post on our [class discord page](https://discord.gg/5Z8Scwhj). We are here to support you and everyone should participate, please.  

## Lab 1 Goals  
The goal of lab 1 is to get everyone started using R, RStudio, and GitHub. All of our work will be done in RStudio and uploaded to the class GitHub repository. It is important that everyone is set-up correctly before we are done today. In the spirit of the R universe, our class is a community. If you see someone struggling, please give them some help.  

## Setup your computer  
Because you will need to work on assignments at home, it is important that you spend time making sure that your computer is set-up and ready to go. The first step in this is basic maintenance; i.e. clean up your desktop and update your OS. Data scientists are neat and tidy! Spend time getting yourself organized, it will pay off.  

Please follow these four steps to set-up you computer [here](https://jmledford3115.github.io/datascibiol/setup.html).  

## GitHub  
[GitHub](http://www.github.com) is a file storage and management site used by programmers. Programmers upload code to repositories (folders) and make it publicly available. We will use Github to store our work in BIS 15L.  

## Your GitHub account  
Since we will use GitHub for assignments, you need to have an account and make a repository for BIS 15L. If you followed the [setup instructions](https://jmledford3115.github.io/datascibiol/setup.html) above then you should be all set. Please [Email](mailto:bymoore@ucdavis.edu) your user name to Bry.    

We have a main repository for our class [datascibiol](https://github.com/jmledford3115/datascibiol). You should **Star** this repository for future reference.  

## Make Your Own Repository  
1. Go to [github.com](www.github.com) and login.  
2. Create a new repository.  
3. Under repository name, use the title `BIS15W2024_your first initial and lastname`. Mine looks like this: BIS15W2024_jledford  
4. Default settings are fine, but do click "Initialize this repository with a README".    
5. Once the repository is made, click on settings in the top right.  
6. On the left toolbar click "Collaborators".  
7. Add "jmledford3115" and "bryshalm" as collaborators.  

## GitHub Desktop  
The easiest way to manage your GitHub repository is to use [GitHub desktop](https://desktop.github.com/). This is a  helpful tool that will allow you to manage all of your files. Open the program and login using your GitHub account.  

## Clone Your Repository  
In GitHub desktop, you will see your personal repository as an option under `clone repository`. Clone your repository to the desktop. Once you have done this any changes you make to files will be recorded and easily uploaded. Do not move this folder from your desktop.  

## Copy the Class Repository
In order to keep track of the class files, the last thing you need to do is make a copy of the class repository. I will make regular changes to the class repository including the addition of files and data that you will need. Do a search for `datascibiol` and download a copy to the desktop. You do this by navigating to the repository then going to the small green code button at top right. Click on the code button then go to Download ZIP.  

Copy the `lab1` folder from the class repository and paste it into your personal repository. By doing this, you have created your own copies of lab materials for lab 1.  

## Using GitHub  
You will use your repository to store all of your notes and work. There are three terms that we need to define:  
1. `Commit` takes a snapshot of your current progress.    
2. `Pull` this is the same as download.     
3. `Push` this is the same as upload.    

If you setup [GitHub desktop](https://desktop.github.com/), then you will see that it automatically tracks your changes. Clicking the `Commit to master` button in the bottom left corner means that you are recording a snapshot of your edits locally. Once this is done, you need to upload your changes to GitHub. This is done by clicking `Push origin`. Once you have pushed your changes you can double check by looking at your repository on github.com.    

## Practice  
Since you will use your GitHub repository extensively in class, we need to practice.  
1. Navigate to your repository and find the file `dummy_push` in the `lab 1` folder.   
2. Open `dummy_push`.  
3. Add your name under `author` at the top of the page.    
4. Save this file.  
5. `Knit` the file.    
6. Use GitHub Desktop to first `Commit to master` and then `Push origin` to your GitHub repository.    

## That's it! Let's take a break and then move on to part 2!

-->[Home](https://jmledford3115.github.io/datascibiol/)  
