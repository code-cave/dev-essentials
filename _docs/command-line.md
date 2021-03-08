# Command Line
The command line is used so much in development that it'd be near impossible  
to be a dev without using it. From navigating the file system, running commands,  
programs, using tools, to connecting to other machines, running scripts, etc.,  
the command line is used so much for various different things.  

Note: this page is about doing basic things on the command line, not scripting.  
But since they're closely related, some details regarding scripting are outlined.

### Content:
- [About Shells](#about-shells)
- [Setting Up The Terminal](#setting-up-the-terminal)
- [Running Commands](#running-commands)

## About Shells
There are a ton of things to know about shells, the basics will be covered here.  
The command line terminal is really just a Shell session. There are many different  
kinds of shells (regarding Linux and Mac) such as the Z Shell (zsh), C Shell (csh),  
Korn Shell (ksh), Fish Shell (fish), Bourne Shell (sh), and, the most widely used,  
Bash Shell (bash). The Bash shell stands for Bourne Again Shell (bash) which is  
an updated version of Bourne shell (sh), the original UNIX shell.  

**Why So Many Shells?**  
Each shell behaves differently with respect to interactions within the terminal.  
A basic example, hitting the up arrow in the Bash Shell will bring up the previously  
executed command, whereas hitting the up arrow in Korn Shell won't do the same.  
There are also some differences in the styling and layout in the different shells.  
The different shell flavors exist for those who have a preference for a particular  
way for the shell to look and behave. Bash is the tried and true shell, and it's the  
industry standard for very good reason in that it's installed in all the Linux and Mac  
distributions and the syntax and commands are just about 99% synonymous with  
the Bourne shell, which is also included in all of the Linux and Mac distributions.  
It's a pretty rare scenario that a difference is found in normal usage or scripting.  
Because of this, Bash can be used in old and new systems alike and everything  
will still work as expected. When connecting to a server via `ssh`, it's normally  
always a Bash session that's opened.  

**When To Use Which Shell?**  
When a terminal is open on the local machine, that's when it's fine to use any of  
the different flavors of shells, it's your machine and you can use what you prefer.  
It's just a shell session afterall. For scripting however, the Bourne shell syntax and  
commands should always be used. This is because every Linux and Mac machine  
has sh installed, the script can be executed on any machine. Connecting to a big  
enterprise Linux server to run a Fish Shell script probably won't work out too well.  
Bourne Shell script files always have a `.sh` file extension and the first line in the  
shell script file (which is required and is called the "shebang") will always have  
the shebang mentioning the path to the sh executable, for example:  
```sh
#! /bin/sh

The rest of the script...
```
Overall, use whatever flavor of shell for the local terminal, and use sh for scripting.  

**What About GNU, And UNIX/POSIX Command Line Tools?**  
There's a long history regarding Linux and the associated command line tools from  
older versions of Linux. Lucky for us in today's world, all of these command line tools  
such as `grep`, `sed`, `awk`, `cat`, and even the humble `cd` and `ls` are all included  
in Bash and Bourne Shell distributions. All that needs to be known about this stuff is  
that at one point in time, there were system specific implementations for these tools  
on very old systems. In today's world, they're all available to use in the different shell  
distributions with no complications.  

All this information about shells is **_good to know_**, but necessarily **_need to know_**.  
Knowing it, however, helps clear up a good bit of confusion with all the terminology.  

## Setting Up The Terminal
The first thing to do is make sure that the preferred shell is the default one.  

To get what the current default shell is, run:  
`echo $SHELL`  
All this command does is prints out the SHELL environment variable (current shell).

To change the default shell to Bash, run the change shell command:  
`chsh -s /bin/bash`  
The default shell can be set to any shell that exists in the /etc/shells file.  
If the desired shell flavor doesn't exist in /etc/shells, it must be installed.  

**Highly Recommended!**  
Install [iTerm](https://iterm2.com/index.html) if on Mac.  
Install [Hyper Terminal](https://hyper.is) if on Linux.

**Also Highly Recommended!**  
Modify the PS1 shell prompt variable in ~/.bash_profile to print the Git branch.  
Towards the bottom of ~/.bash_profile, add the following:  
```sh
git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

PS1="\[\033[00m\]\n\u@\h \[\033[32m\]\w\[\033[33m\]\$(git_branch)\n\[\033[34m\]\$ \[\033[00m\]"
```
It's **really handy** having the current git branch displayed when in a repository.  

**What Is .bash_profile And .bashrc?**  
The .bash_profile and/or .bashrc files are executed when an interactive shell session  
is opened, such as opening up the terminal in Mac or Linux. The difference between  
the two, is that .bash_profile is executed when the shell is an interactive login shell,  
and .bashrc (means Bash Run Commands) is executed for interactive non login shells.  
A good .bash_profile will source the .bashrc file so that a login shell gets the content  
contained in both files. For example, if you open the terminal on a Mac or Linux box,  
then the .bash_profile file on the machine is executed when the shell session starts.  
If you run a process that creates an interactive non login shell, like vim or some other  
text editor or interactive process, then .bashrc is sourced.

## Running Commands
There's only one way to get better at something, and that's by doing it.  
Learn to use the following commands:  
- `ls` list the contents of a directory
- `mkdir` make a directory
- `cd` change to a directory
- `>some-file.txt` shorthand to create a file
- `echo` print text
- `cat` concatenate file
- `rm` remove files or directories - **NEVER** run `rm -rf /`, it will ruin a machine
- `grep` print matching lines of text in a file
- `sed` modify text that matches a regex pattern

For information on the commands, run `man <command_name>`  
There are plenty of examples for these commands online as well.

These are the basics that every developer should know how to use well.

