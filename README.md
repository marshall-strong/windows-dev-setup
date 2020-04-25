# windows-dev-setup
Instructions for setting up a development environment on your Windows computer. Compatible with appAcademy curriculum.

https://open.appacademy.io/learn/swe-in-person/software-engineering-foundations/ruby-environment-setup


Chrome
======
Install Google Chrome: https://www.google.com/chrome/


Visual Studio Code (Part 1)
=================
Setup Visual Studio Code: https://code.visualstudio.com/docs/setup/

Install the user setup: https://code.visualstudio.com/docs/setup/windows

Select Additional Tasks
+ Add “Open with Code” action to Windows Explorer file context menu
+ Add “Open with Code” action to Windows Explorer directory context menu
+ Register Code as an editor for supported file types
+ Add to PATH (requires shell restart)




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

Bash Profile
`~/.bashrc`


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

Your GitHub password will be stored separately. There are several different ways to do this. The simplest is to use [git-credential-store](https://git-scm.com/docs/git-credential-store).
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



Visual Studio Code (Part 2)
=================

Extensions
---------
+ Remote - WSL
 Install: https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl
 Developing in WSL documentation: https://code.visualstudio.com/docs/remote/wsl
 WSL step-by-step tutorial: https://code.visualstudio.com/remote-tutorials/wsl/getting-started



rbenv and Ruby
======

https://github.com/rbenv/rbenv-installer#rbenv-installer
https://unix.stackexchange.com/questions/378060/gcc-error-no-acceptable-c-compiler-found-in-path/545756#545756?newreg=41bcf4b931f8449287d1eb828df10b1f


Install rbenv using curl
+ `curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash`

Add rbenv to PATH by configuring your `~/.bashrc` file
+ `echo '' >> ~/.bashrc`
+ `echo '# add rbenv to PATH' >> ~/.bashrc`
+ `echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc`
+ `echo '# initialize rbenv everytime you open a new console window (otherwise our system ruby version will take over when we start a new terminal session)' >> ~/.bashrc`
+ `echo 'eval "$(rbenv init -)"' >> ~/.bashrc`

Install prerequisites
+ `sudo apt-get update`
+ `sudo apt install build-essential`
+ `sudo apt-get install -y libssl-dev libreadline-dev zlib1g-dev`
If you try to install ruby before doing this step, you will get an error message: 
 configure: error: in `/tmp/ruby-build.20200422222351.960.zIwDA8/ruby-2.5.1':
 configure: error: no acceptable C compiler found in $PATH`

Install Ruby 2.5.1 
+ `rbenv install 2.5.1`

Set Ruby version 2.5.1 to be our global default
+ `rbenv global 2.5.1`
The 'rehash' command updates the environment to your configuration
+ `rbenv rehash`

Verify that Ruby was installed correctly:
Check the version
+ `ruby -v` # => ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-linux]
Check that we are using rbenv (this tells you where the version of ruby you are using is installed)
+ `which ruby` # => /Users/your-username/.rbenv/shims/ruby

Ruby Gems
==========
RubyGems is Ruby's package manager. It helps developers download, develop, and distribute Ruby applications, which are known as Gems.

Bundler
-------
+ `gem install bundler`
 Bundler allows us to define project dependencies inside a Gemfile and gives us a bunch of commands to update, remove and install them. Check out the [Bundler docs](https://bundler.io/docs.html) for more info.

Pry
----
 + `gem install pry`
 Pry is an alternative to the Irb (the default Ruby REPL). It is not only more powerful, but also easier to use than Irb and should be your go-to for running and debugging Ruby code. Check out the [Pry website](https://bundler.io/docs.html) for more info and a super useful tutorial.

Byebug
-------
+ `gem install byebug`
 Byebug is feature-rich debugging tool for Ruby. With Byebug you can halt the execution of your code and inspect/track variables and the flow of execution. Lots of cool features in here, so check out the [Byebug docs](https://github.com/deivid-rodriguez/byebug)!

Ruby on Rails
-------
+ `gem install rails --version 5.2.3`
 Rails is Rails


PostgreSQL
==========
[Microsoft documentation](https://docs.microsoft.com/en-us/windows/nodejs/databases#install-postgresql)
Installation
-----------
Open your WSL terminal (ie. Ubuntu)
Update your Ubuntu packages:
+ `sudo apt update`
Install PostgreSQL package
+ `sudo apt install postgresql`
Install postgresql-contrib package (contains some helpful utilities)
+ `sudo apt install postgresql-contrib`
Confirm installation and get the PostgreSQL version number:
+ `psql --version`

There are 3 commands you need to know once PostgreSQL is installed:
`sudo service postgresql status` for checking the status of your database.
`sudo service postgresql start` to start running your database.
`sudo service postgresql stop` to stop running your database.

PostgreSQL User Setup
-----------------
The default admin user, postgres, needs a password assigned in order to connect to a database. To set a password:

Enter the command: `sudo passwd postgres`
You will get a prompt to enter your new password. (postgres)
Close and reopen your terminal.

Run PostgreSQL with psql shell
----------------------------
psql is a terminal-based front-end to PostgreSQL. It enables you to type in queries interactively, issue them to PostgreSQL, and see the query results.

To start the psql shell:

Start your postgres service: sudo service postgresql start
Connect to the postgres service and open the psql shell: sudo -u postgres psql
Once you have successfully entered the psql shell, you will see your command line change to look like this: postgres=#

To exit postgres=# enter: \q or use the shortcut key: Ctrl+D

To see what user accounts have been created on your PostgreSQL installation, use from your WSL terminal: psql -c "\du" ...or just \du if you have the psql shell open. This command will display columns: Account User Name, List of Roles Attributes, and Member of role group(s). To exit back to the command line, enter: q.

VS Code support for PostgreSQL
-------------------------
VS Code supports working with PostgreSQL databases via the PostgreSQL extension, you can create, connect to, manage and query PostgreSQL databases from within VS Code.



SQLite
===========
SQLite is a small, lightweight database application that requires no configuration and stores the database as a stand-alone file. 
AppAcademy uses SQLite for several in-class projects.

Install
-------
`sudo apt install sqlite3`






Node.js
=========
Node.js will be our local JavaScript engine. This is used to run JavaScript code and run associated node commands.
Again, we want to use a version manager with Node to help us manage potential conflicts between versions and dependencies. In this case we will be using NVM (Node Version Manager) to install/manage Node.js.

Install NVM
`curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.6/install.sh | bash`

Update your terminal config (you will now have access to the nvm command)
`source ~/.bashrc`

Install node (the AppAcademy curriculum uses 10.13.0, a stable version)
`nvm install 10.13.0`

Set version 10.13.0 as default node version
`nvm use 10.13.0`

Verify install/config
`which node` # => /Users/username/.nvm/versions/node/v10.13.0/bin/node

Node, like Ruby, comes with a package manager called NPM, which provides access to a whole ecosystem of libraries and tools we can use. 
NPM comes pre-bundled with Node, so there is no additional work for us to do. 
We don't need NPM to install any additional packages by default, as we will be installing them on a per-project basis.






