# windows-dev-setup
Instructions for setting up a development environment on your Windows computer. Compatible with appAcademy curriculum.

https://open.appacademy.io/learn/swe-in-person/software-engineering-foundations/ruby-environment-setup



Windows Insider Program
=======================

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






Windows Terminal
================

Install: https://www.microsoft.com/p/windows-terminal-preview/9n0dx20hk701?SilentAuth=1&wa=wsignin1.0&activetab=pivot%3Aoverviewtab




RBENV
======

https://github.com/rbenv/rbenv-installer#rbenv-installer
https://unix.stackexchange.com/questions/378060/gcc-error-no-acceptable-c-compiler-found-in-path/545756#545756?newreg=41bcf4b931f8449287d1eb828df10b1f




POWERSHELL
======
https://www.howtogeek.com/163127/how-powershell-differs-from-the-windows-command-prompt/

https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/


https://haacked.com/archive/2011/12/19/get-git-for-windows.aspx/
https://haacked.com/archive/2011/12/13/better-git-with-powershell.aspx/

t

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








Use Git-Credential_Manager-for-Windows to store your github password
https://github.com/Microsoft/Git-Credential-Manager-for-Windows
Download GCM installer: https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest



https://gitforwindows.org/
https://help.github.com/en/github/using-git/caching-your-github-password-in-git

Use Windows Credential Manager to store GitHub credentials
https://snede.net/git-does-not-remember-username-password/



user.name=marstrong
user.email=marshallstrong123@gmail.com
credential.helper=manager
credential.manager=wincred
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
remote.origin.url=https://github.com/marstrong/windows-dev-setup.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.master.remote=origin
branch.master.merge=refs/heads/master
branch.console_output_files.remote=origin
branch.console_output_files.merge=refs/heads/console_output_files
branch.more_console_history.remote=origin
branch.more_console_history.merge=refs/heads/more_console_history
