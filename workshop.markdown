---
layout: page
title: Workshop
permalink: /workshop/
---

Does your research require you to build a static website to document your project or disseminate information as part of a knowledge mobilization requirement? In this workshop you will learn how to build a Jekyll static website using GitHub pages. You will learn some command line fundamentals and be introduced to Jekyll, Ruby, Git and GitHub. By the end of the workshop you will have your own Jekyll website hosted on GitHub pages.

For this workshop we are going to build your Jekyll site and then upload it to GitHub using Git commands in your command line interface. Once the Jekyll website repository is uploaded to GitHub, we will configure your Jekyll repository to GitHub pages, which will make your project a live website.

## Build a Jekyll Site
Before we begin the workshop you need to make sure Jekyll is installed on your machine. Make sure to consult the [Setup page](https://ludicpress.github.io/staticsites/setup/) if you have not installed Jekyll on your Linux, Windows or OS X machines.

The first thing we will do is create a Jekyll website based on its default template. At the command line, type in the following and hit enter. Note, where I have typed in ```jekylldemo``` you can type anything, but keep in mind this will be the name of your Jekyll website repository:

```jekyll new jekylldemo```

This command told Jekyll to create a new site by installing all the necessary files in a folder names ```jekylldemo```. This folder will be referred to as the website folder for the rest of the workshop. 

You have created your first static site, congratulations! Obviously, there is still a lot more work to do in terms of adding content, but now we can move onto the next stage and add the site to GitHub using Git.

## GitHub
Before we can use Git to upload our website folder to GitHub, we need to create a GitHub user account. A GitHub user account will let you host your website for free on GitHub. In addition, GitHub will also let you keep track of versions of the website and its writing as it grows or changes over time.

Visit GitHub.com and click on the “Sign up” button on the upper right. Write your desired username. This will be visible to others, identify you on GitHub, and also be part of your site’s URL; for example, this author’s GitHub username is ludcipress and hia demo statis site’s URL is http://ludicpress.github.io/jekylldemo/. (Note you can also purchase your own domain name and use it for this site, but that won’t be covered in this workshop). Also write your desired email address and password, then click “Create an account”.

On the next page, click the “Choose” button next to the “Free” plan option, ignore the “Help me set up an organization next” checkbox, and click “Finish sign up”.

Optional: Visit https://github.com/settings/profile to add a full name (can be your real name, GitHub user name, or something else) and other public profile information, if desired.

Now that you have a GitHub account we can upload your website folder to GitHub using Git in the command line. However, we first need to create a new repository in GitHub so we have somewhere to send our website folder. While still logged in to GitHub you can add a new repository by clicking on the ```+``` icon in the top right-hand side of the page. Select the option ```new repository```. In the new repository, use the same name as the project folder and select the option ```Public``` before clicking the ```Create repository``` button. This ensures your site will be live when you upload the website folder. Keep the next page open as you'll need it for the next step.

## Git
Now that we have a repository we need to use Git to upload our website folder. On the GitHub page after you created the repository there should be a link that looks something like this:

```https://github.com/ludicpress/jekylldemo.git```

This is the web address that your website folder will use to push its contents to the repository on GitHub. Copy this link and go back into your command line interface.

Next we need to go into the website folder using the ```cd``` command:

```cd jekylldemo/```

Next we need to track your files, but the terminal needs to know who is doing the tracking. In your command line, type and enter:

```git config --global user.email "you@example.com"```  
```git config --global user.name "your name"```

Next we need to initialize our webfolder into a Git repository using the following command:

```git init```

To track our files we need to add them to git. To add all the files we use the following command. Note the space before the perdiod ``` .``` is important:

```git add .```

To check and make sure all our files have been added, we can use the Git status command:

```git status```

Now that the files are tracked we can:

```git remote add origin [your copied URL]```

Mine looks like this:

```git remote add origin https://github.com/ludipress/jekylldemo.git```

You will then need to initialize your first commit:

```git push -u origin master```

You will be prompted to sign in with your username and password for your GitHub account.

Wait a few moments for the task to be complete. Once your command prompt reappears go back into your GitHub repository and refresh your webpage. The website folder with all your files should now be there.

But wait! You have one last step to complete before your site is live. In GitHub, click on branch and type in a new branch labelled ```gh-pages``` in the name field and then click ```Create branch```. Make sure this branch is your default branch so any changes you make are made to your website and not the original master file you uploaded. 

You can now visit your static site. The URL of your website will look like the following:

```username.github.io/websitefolder/```

My site looks like:
```ludicpress.github.io/jekylldemo/```

## Edit your Static Site  
Congratulations, your static site is live! But there is still so much more you can do! It also may not look much like a website if some of the settings are missing from the ```_config.yml``` file. In this next section I will give an overview of how to navigate your website folder files and edit those files which represent your web pages, posts, and templates.

From now on all edits you make can be done in the GitHub interface. The first thing we need to go is edit the ```_config.yml``` file and make sure some of our build settings are good. Open up the file and click on the little pencil icon to edit the file. Here you can edit your ```Site Settings``` and ```Build Settings```.

In the site settings, make sure to change your title, email, description, twitter name and github name. However, more importantly you want to change the base URL to the subpath of your site, such as:

```/jekylldemo```

And the URL of your hostname to:

```localhost:4000```

This is important as it tells your config file what your URL is supposed to be (i.e., ludicpress.github.io/jekylldemo).

Next we need to check the Build Settings. This is usually the reason why your site might look funky on installation. You should see the following information in the build settings:

```markdown: kramdown```  
```theme: minima```  
```plugins:```  
```  - jekyll-feed```

If not, copy and paste the above and put it just below the build settings heading. Make sure to commit your changes. Wait a minute or so and refresh the website. Your website changes should now be visible and look like a minimal static website.

## Edit and Create Content
To create new pages and posts for your website, you simply need to create a new file in your repository with a file name and markdown at the end of it. For example, to create a new page, click ```Create new file``` and type in your file name with markdown:

```research.markdown```

This tells your repository that this is a Markdown file that will be titled 'Research'. Next you will need to give the file instructions so it knows what kind of file it is. Within the file at the top of the document type or copy and paste the following:

```---```  
```layout: page```  
```title: Research```  
```permalink: /research/```  
```---```

For your research file it needs to know what type of layout it should use (i.e., page). Once that information is inserted you can enter the title of the page followed by the what you would like the permalink to be enclosed within two slashes. Note, the three dashes above and below these instructions are important.

Below this information you can insert text, links, and whatever you like following the Markdown syntax. Check the [Resources page](https://ludicpress.github.io/staticsites/resources) to find more information on how to use Markdown in editing your pages.

Creating posts is very similar to pages except for two small changes. When you create a post you ```Create a file``` within the ```_posts``` folder. 

After you name your file with Markdown at the end you need to insert the following information at the top of your file. Note, the name you give your post is derived from the file name you give it (e.g., /welcome-to-the-jekyll-demo/):

```---```  
```layout: post```  
```title:  "Welcome to the Jekyll Demo!"```  
```date:   2019-11-19 12:00:13 -0500```  
```categories: jekyll```  
```---```

Instead of ```page``` you insert ```post``` in the layout section. It's then important you title your post, provide a time and date, and then create a category for how you will categorize your post. This means as you accumulate posts users can search for them based on the categories you create.

As with pages, you can insert, text, links and what you like following the Markdown syntax.

## Final Thoughts
There is still plenty more to learn with Jekyll and GitHub pages. There are also dozens, if not hundreds, of themes available to use instead of the Minima theme that comes with this tutorial. In addition, there are many digital research groups creating static page themes in Jekyll, such as the [Minimal Computing](https://github.com/minicomp) for digital editions, digital exhibits, and a range of other static sites for humanities and social science projects. If this is your first time with static sites, don't be dismayed by the learning curve or the simplicity. The payoff can be great depending on your digital research goals and projects.
