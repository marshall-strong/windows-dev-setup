# windows-dev-setup
Instructions for setting up a development environment on your Windows computer. Compatible with appAcademy curriculum.

https://open.appacademy.io/learn/swe-in-person/software-engineering-foundations/ruby-environment-setup


Chrome
======
Install Google Chrome: https://www.google.com/chrome/


Visual Studio Code
=================
Setup Visual Studio Code: https://code.visualstudio.com/docs/setup/

Install the user setup: https://code.visualstudio.com/docs/setup/windows

Select Additional Tasks
+ Add “Open with Code” action to Windows Explorer file context menu
+ Add “Open with Code” action to Windows Explorer directory context menu
+ Register Code as an editor for supported file types
+ Add to PATH (requires shell restart)

Extensions
---------
+ Remote - WSL
Install: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
Developing in WSL documentation: https://code.visualstudio.com/docs/remote/wsl
WSL step-by-step tutorial: https://code.visualstudio.com/remote-tutorials/wsl/getting-started




Windows Insider Program
=======================
Join the Microsoft Windows Insider program to download the latest version of Windows 10
Microsoft Windows Insider: https://insider.windows.com/en-us/


Windows Subsystem for Linux
===========================
With WSL, you can install and run Linux distributions on Windows. This enables you to develop and test your source code on Linux while still working locally on your Windows machine.

WSL FAQ: https://docs.microsoft.com/en-us/windows/wsl/faq

WSL
---

Install WSL: https://docs.microsoft.com/en-us/windows/wsl/install-win10

WSL 2
-----

Install WSL 2: https://docs.microsoft.com/en-us/windows/wsl/wsl2-install



Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1804 -OutFile Ubuntu.appx -UseBasicParsing

Things you might have encountered/have questions about:
--------------
+ What is MSYS2?
 MSYS2 allows you to use many Unix/Linux tools and utilities inside of a Windows environment. Basically, it makes Windows more like Linux. We don't need MSYS2 since we won't actually be developing in the Windows environment -- we'll be using the Linux subsystem we installed instead.

+ What is MinGW?
 MinGW is an open source software development environment for creating Windows applications. We'll be using the Linux subsystem we installed instead. 


BASH
====
Various ways of opening a bash console...
---

The stuff no one tells you:
---
Home directory: /home/marstrong
Home directory shortcut: ~
The following commands will all do the same thing:
+ `cd /home/marstrong`
+ `cd ~`
+ `cd`

+ `.` current directory
+ `..` up one directory 


+ hidden files and directory start with `.`
+ `ls /home/marstrong -a` list all files in directory, including hidden files


Git
===

Download Git for Windows
------------------------
Link: https://gitforwindows.org/
Click the 'Download' button
(Direct Link: https://github.com/git-for-windows/git/releases/download/v2.26.2.windows.1/Git-2.26.2-64-bit.exe)

Install Git for Windows
------------------------
Run the .exe file you just downloaded. This will open a Git Setup dialog.
+ Default options are fine for the 'Select Components' section.
+ Select Visual Studio Code as Git's default editor.
+ Select 'Git from the command line and also from 3rd-party software'
+ Select 'Use the OpenSSL library' for HTTPS connections
+ Select 'Checkout Windows-style, commit Unix-style line endings'
+ Select 'Use Windows' default console window' as the terminal emulator to use with Git Bash
+ Select 'Enable file system caching' and 'Enable Git Credential Manager' ?
Click the 'Install' button

Create GitHub account
---------------------
+ Email, Username, Password
+ Create new repo, initialize with readme
+ Copy link for cloning repo

Configure Git
------------
Open a new bash console
Clone your repo repo using bash command line
+ `git clone https://github.com/marstrong/windows-dev-setup.git`
Make some changes to the readme
+ `git add -A`
+ `git commit -m "first commit"`

At this point, if you attempt to push your changes to GitHub, Git will ask who you are. It will then prompt you to run the following commands.
+ `git config --global user.email "you@example.com"`
+ `git config --global user.name "Your Name"`
Replace "you@example.com" with your own email inside double quotes
Replace "Your Name" with your own GitHub username

These values are stored in the .gitconfig file
Open your .gitconfig file
+ `code ~/.gitconfig`
You should notice that your email and username have been added to the file
Let's tell git to use pretty colors
+ `git config --global color.ui true`
You should immediately see the change reflected in the .gitconfig file

Your GitHub password will be stored separately. There are several different ways to do this. The simplest is to use git-credential-store.
+ `git config --global credential.helper 'store'`
The next time you attempt to push to GitHub, Git will prompt you for your username and password. Git will save the credentials you entered in an unencrypted text file. 
+ `code ~/.git-credentials`
This is not particularly secure, but you probably already knew that. 

Make some more changes, then push again
+ `git add --all`
+ `git commit -m "test git-credential-store"`
+ `git push`
You won't be prompted for any credentials, nor will you ever again. 

There are plenty of other ways to store your GitHub password, and you're welcome to explore them!
+ Use Git-Credential_Manager-for-Windows to store your github password: 
    - https://snede.net/git-does-not-remember-username-password/
    - https://github.com/Microsoft/Git-Credential-Manager-for-Windows
+ Download GCM installer: https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest




So far, we have been configuring Git at the global level using `git config --global`. This stores our configuration settings in a file at the root of the home directory: `~/.gitconfig`.

Configuration settings that are specific to a single repository can be set using `git config --local`. The settings are stored in a file at the root of the repository's directory: `/repo/.git/config`

If you ever lose track of where your various configurations are coming from, run the following command:
+ `git config --list --show-origin`


Windows Terminal
================

Install: https://www.microsoft.com/p/windows-terminal-preview/9n0dx20hk701?SilentAuth=1&wa=wsignin1.0&activetab=pivot%3Aoverviewtab





POWERSHELL
======
https://www.howtogeek.com/163127/how-powershell-differs-from-the-windows-command-prompt/

https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/


https://haacked.com/archive/2011/12/19/get-git-for-windows.aspx/
https://haacked.com/archive/2011/12/13/better-git-with-powershell.aspx/


RBENV
======

https://github.com/rbenv/rbenv-installer#rbenv-installer
https://unix.stackexchange.com/questions/378060/gcc-error-no-acceptable-c-compiler-found-in-path/545756#545756?newreg=41bcf4b931f8449287d1eb828df10b1f

NEXT
====

























