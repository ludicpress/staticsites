---
layout: page
title: Setup
permalink: /setup/
---

Before we start the workshop component of how to build a static website with Jekyll and GitHub for digital research there is some preliminary setup we have to complete on your computer. There are several ways to install the different components we need to create a static Jekyll website on GitHub. We will approach setup through the command line. Depending on which operating system you use, setup can be straightforward or the most time consuming aspect of learning how to build a Jekyll website on GitHub pages. Below are installation instructions for Linux, Windows, and OS X users. Once Jekyll is installed on each system, the instructions will be the same for every user participating in the workshop.

## Linux Instructions
If you are using a Linux operating system, the instructions for Jekyll installation are relatively straightforward compared to Windows and OS X. Before we install Jekyll, we need to make sure we have all the required dependencies--specifically, Ruby and its Gems. Ruby is the programming language that will enable us to install Jekyll and create our static website.

Open the command line interface on your Linux system and type in the following command and hit enter:

```sudo apt-get install ruby-full build-essential zlib1g-dev```

It is best to avoid installing Ruby Gems as the root user. Therefore, we need to set up a gem installation directory for your user account. The following commands will add environment variables to your ```~/.bashrc``` file to configure the gem installation path. Type in the following commands sequentially and hit enter:

```echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc```  
```echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc```  
```echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc```  
```source ~/.bashrc```  

Now that we have configured a path for your Jekyll installation we can complete the setup with the following command:

```gem install jekyll bundler```

When the prompt returns we can check to see if Jekyll is running smoothly by entering the following command:

```jekyll -v```

If Jekyll is not installed type in the following command and hit enter:

```sudo apt install jekyll```

If prompted, type ```y``` and hit enter.

Try the version command again and the following message should now display in your prompt:

```jekyll 4.0.0```

At the time of writing Jekyll was upgraded to 4.0, but there may be a later version depending on when you read this documentation. Now that you have completed the setup and installation of jekyll you can move on to the workshop!

## Windows Instructions
To install Jekyll we have to activate the Windows Subsystem for Linux (WSL) and install a Linux distro (i.e., command line). For this workshop we will use the Ubuntu application on Windows, but first we have to activite the WSL.

To activate the WSL, open Powershell as an Administrator. To do this, type in Powershell in the Windows search bar in the bottom left corner of your screen. The application Windows Powershell Ise will appear. On the right-hand side of the window will be the option 'Run as administrator'. Select Run as administrator and enter your administrative login credentials if prompted. If you do not run Powershell as an administrator the next step will not work.

In the Powershell terminal that opens up, copy and paste the following command and hit enter:

```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux```

Restart your computer when prompted to do so.

Once your computer has restarted, open the Microsoft Store. You can access the Microsoft Store by typing Microsoft Store in the Windows search bar and select open from the right-hand side of the window. When the Microsoft Store opens, type 'Ubuntu' into the search bar. Several Ubuntu applications will appear in the search results. Select the app that is only titled 'Ubuntu' and developed by Canonical Group Limited.

Click install and wait for the Ubuntu application for Windows to install. Once the application has installed, type Ubuntu in the Windows search bar and open the application. Note, you do not need to Run as administrator for this application. The Ubuntu application will take approximately 5 to 10 minutes to install, so do not worry if it does not open right away.

When Ubuntu opens for the first time you will be prompted to create a username and password. Create your username and hit enter. Create your password and hit enter. A re-enter password prompt will appear and re-enter your password. Your username and password should now be created. Whenever you open Ubuntu and try to install software you will be prompted for your username and password.

The next few steps are relatively time consuming, but they are necessary to make sure we install Ruby and then Jekyll on to your computer using Bash for Windows. In the Ubuntu command prompt type in the following command and hit enter:

```bash```

Your command prompt instance should now be a Bash instance. The colour of your command prompt will likely have changed to another colour (in my case, green). Next we need to update our Bash repository lists and packages to make sure our instance of Bash is up-to-date. In the command prompt type in the following command and hit enter:

```sudo apt-get update -y && sudo apt-get upgrade -y```

The first part before the ```&&``` updates the Bash repository lists and the second part following the ```&&``` upgrades the Bash packages. At this point you will be asked to restart services during package upgrades without asking. When prompted select ```<Yes>```and hit enter. When you select ```<Yes>``` it means you won't be asked to install every single package, and there are a lot of packages! This may take several minutes (almost 15 minutes when I timed it!), so hang tight and wait for the prompt to reappear.

When the prompt reappears we can check to make sure Bash was installed properly. In the command prompt type in the following command and his enter:

```bash --version```

If all went well, the following information should display on your machine:

```GNU bash, version 4.4.20(1)-release (x86_64-pc-linux-gnu)```  
```Copyright (C) 2016 Free Software Foundation, Inc.```  
```License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>```  
```This is free software; you are free to change and redistribute it.```  
```There is NO WARRANTY, to the extent permitted by law.```

At the time of writing this documentation Bash was at the latest version 4.4.20. If your computer does not install to the latest version it may be that you do not have full privileges on the computer you are using.

Next we need to install Ruby. Ruby is the programming language that will enable us to install Jekyll and create our static website. To install Ruby we will use a repository from BrightBox, which hosts optimized versions of Ruby for Ubuntu--this is perfect for us. 

In the command prompt type in the following commands and hit enter. Remember to wait for the prompt before entering each line of code.

First:  
```sudo apt-add-repository ppa:brightbox/ruby-ng```

Second:  
```sudo apt-get update```

And third:  
```sudo apt-get install ruby2.5 ruby2.5-dev build-essential dh-autoreconf```

If prompted, hit ```[ENTER]```, type ```y```, or select ```<YES>``` and hit enter. This may take several minutes to complete the whole installation process. By this point, you are probably tired of waiting, but hold tight as we're getting to the end of the setup!

Next, we need to install Ruby:

```apt install ruby```

If prompted select yes or type ```y``` and hit enter. Note, you may need to use sudo before this command and the following commands if you receive a message stating you do not have privileges to make the necessary changes.

Now that Ruby is installed we need to update our gems. Gems are packages within Ruby that make it easy for us to install programs, like Jekyll, with a simple command. To update our gems, type the following into the command prompt and hit enter:

```gem update```

Now that the gems have been updated, we can install Jekyll. In the command prompt type in the following command and hit enter:

```gem install jekyll bundler```

When the prompt returns we can check to see if Jekyll is running smoothly by entering the following command:

```jekyll -v```

If Jekyll is not installed type in the following command and hit enter:

```sudo apt install jekyll```

If prompted, type ```y``` and hit enter.

Try the version command again and the following message should now display in your prompt:

```jekyll 4.0.0```

At the time of writing Jekyll was upgraded to 4.0, but there may be a later version depending on when you read this documentation. Now that you have completed the setup and installation of jekyll you can move on to the workshop!

## OS X Instructions
To install Jekyll on OS X there are several dependencies we need to install, including Apple's Command Line Tools and Homebrew. This requires downloading XCode. If you have the App Store, you should be able to just download XCode.  If not, the following instructions will work.

To download this, go to the Apple Developer website, register as a developer, and then in the downloads for Apple developers section you will need to find the correct version. If not, you will need to click on the link: “Looking for additional developer tools? View Downloads.”

After logging in with your free developer credentials, you will see a long list. Type ```xcode``` in the search bar and find a version that is compatible with your operating system version. This may take some clicking around to find the right version for you. For example, Xcode 3.2 is the version for OS X 10.6 Snow Leopard, 3.0 is the version for OS X 10.5 Leopard, etc.

It is a big download, and will take some time. Once you have the file, install it (when I timed the download it took almost 15 minutes!).

You will need to install the ‘Command Line Tools’ kit in XCode. Open up the ‘Preferences’ tab, click on ‘Downloads,’ and then click ‘Install’ next to Command Line Tools. We are now ready to install a package manager.

The easiest package manager to install is Homebrew. Go to https://brew.sh and review the instructions. There are many important commands, like Jekyll, that are not included by default in OS X. This program facilitates the downloading and installation of all required files.

To install Homebrew, open up your terminal window and type the following:

```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

This uses the ruby programming language, built into OS X, to install Homebrew. If prompted to press ```RETURN``` hit returnTo see if the installation worked, type the following into your terminal window:

```brew```

A list of documentation options should appear if it has been installed. We have one more command to run to make sure everything is working, which is:

```brew doctor```

With Homebrew installed, we now have to install Ruby. Ruby is the programming language that will enable us to install Jekyll and create our static website. Type in the following command and hit enter:

```brew install ruby```

Don’t forget to wait until the command prompt appears again to type in the following command which will update our gems to install Jekyll:

```gem install rubygems-update```

If you get a permissions error at this point, entering ```usr/local/bin/gem install rubygems-update``` instead of the command above may help.

Next, we need to install NodeJS, which is a development tool that makes things like Javascript run faster. Type in the following command and hit enter:

```brew install node```

We're now in the final stretch where we can use our gems to install Jekyll. Type in the following command and hit enter:

```gem install jekyll```

If you get a permissions error at this point, entering ```usr/local/bin/gem install jekyll``` instead of the command above may help.

At the command line, type in the following command and hit enter to install Jekyll on your machine:

```gem install jekyll bundler```

Finally, let's check our version of Jekyll to make sure it is running:

```jekyll -v```

If all has gone according to plan you should see the following print out in your terminal:

```jekyll 4.0.0```

At the time of writing Jekyll was upgraded to 4.0, but there may be a later version depending on when you read this documentation. Now that you have completed the setup and installation of jekyll you can move on to the workshop!
