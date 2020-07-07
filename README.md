# Optional Installation Instructions

## Introduction

The tools in this lesson are not specifically required, but they are things we
recommend based on previous student experiences. Feel free to pick and choose
what you would like to use and install.

### Customizing Your Terminal Prompt

When writing a command in the terminal, everything to the left of your command
is referred to as your terminal's _prompt_. At the moment, your prompt may include
something like your username for the computer. 

You can also customize your prompt to display whatever you'd like by configuring it
in `~/.zshrc`. Open `~/.zshrc` in your text editor. You should see something similar to
the following after following the macOS environment instructions:

```sh
# Do not modify these three lines - this code loads Node Version Manager 
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Do not modify the line below
# Add RVM to PATH for scripting. Make sure this is the last PATH variable change.
export PATH="$PATH:$HOME/.rvm/bin"
```

These lines were added during your environment setup. The first set ensure that NVM is loaded and
available in the terminal. The last lines ensure RVM looks in the correct places for versions of Ruby.
To add a customized prompt, we want to add a bit of code into this file:

```sh
function prompt {
    local CHAR="♥" ## ♥ ☆ ♬ ○ ♩ ● ♪ - Keeping some cool ASCII Characters for reference
    autoload -U colors && colors
    
    ## Here is where we actually export the PS1 Variable which stores the text for your prompt
    PS1="%{$fg[green]%}%(4~|%-1~/.../%2~|%~) %{$reset_color%}%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}%{$CHAR%} > %{$reset_color%}% "
    PS2='> '
    PS4='+ '
}

prompt
```

This code defines a Zsh function that sets the prompt. Add this in between the NVM and RVM setup
lines. The `~/.zshrc` file should now look like this:

```sh
# Do not modify these three lines - this code loads Node Version Manager 
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion


# The following function sets the terminal prompt
# Modify PS1 to customize it further

function prompt {
    local CHAR="♥" ## ♥ ☆ ♬ ○ ♩ ● ♪ - Keeping some cool ASCII Characters for reference
    autoload -U colors && colors
    
    ## Here is where we actually export the PS1 Variable which stores the text for your prompt
    PS1="%{$fg[green]%}%(4~|%-1~/.../%2~|%~) %{$reset_color%}%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}%{$CHAR%} > %{$reset_color%}% "
    PS2='> '
    PS4='+ '
}

prompt


# Do not modify the line below
# Add RVM to PATH for scripting. Make sure this is the last PATH variable change.
export PATH="$PATH:$HOME/.rvm/bin"
```

Once this file is saved, in your terminal, run `source ~/.zshrc`. You should see your prompt
change to look like this:

```sh
~ // ♥ >
```

This configuration displays the directory you are in, but you can customize
this prompt to include many other helpful things such as the current time. To
change the prompt further, in `~/.zshrc`, modify the line starting with `PS1`. If you make
a change, run `source ~/.zshrc` to see it in the current terminal.

**Note:** If you mess up, either replace the code in `~/.zshrc` with the code snippet above. You can also delete the entire `prompt` function and subsequent `prompt` call (make sure to leave the settings for NVM and RVM). This will return your prompt to the default.

### Key Repeat

Turn up your key repeat. Open System Preferences by clicking the apple icon in
the top left corner of your screen and selecting System Preferences. Then Click
Keyboard and make sure both Key Repeat and Delay Until Repeat are turned up all
the way. This will allow you to move your cursor through text much faster.

### Install DB Browser for SQLite

Install the DB Browser for SQLite at https://sqlitebrowser.org/

This tool helps you visualize and interact with database tables, which will be
helpful as you learn SQL.

### Install Postico for PostgreSQL

[Postico](https://eggerapps.at/postico/) is a user friendly interface for 
looking at PostgreSQL databases created locally.

If you haven't installed PostgreSQL, run the following three commands before 
downloading Postico:

```bash
brew install postgres
brew services start postgresql
gem install pg
```

### Protecting Your Eyes

Programming involves a lot of staring at a computer screen for many hours at a
time. This can sometimes lead to digital eye strain, causing soreness, irration,
dry eyes, fatigue, etc... Staring at a computer screen late into the night can
also potentially impact your ability to get a good night's rest.

For these reasons, we love using [f.lux](https://justgetflux.com/)! f.lux
adjusts your screen's brightness depending on the lighting and the time of day /
sun level in the sky, for ease on your eyes and to help you sleep. Play around
with the settings. It's subtle, but makes a **huge** difference, especially if
you're working late on your computer.

### App Launchers

As of Mac OS 10.4 Tiger, an app launcher is already provided with the Mac OS
called Spotlight. To use Spotlight, press the command (`⌘`) and spacebar buttons
at the same time to bring Spotlight up. To use it, begin typing the name of the
application you want to launch. Spotlight will try to predict what you want, so
you often only have to type the first few letters of the application's name. Much
faster than having to click through folders!

Some common alternatives include:

[Quicksilver](http://qsapp.com/) - A free, tried and true alternative app launcher.

[Alfred 2](http://www.alfredapp.com/) - This is a very popular option, but costs
money to unlock some of the power features.

[Launchbar](http://www.obdev.at/products/launchbar/index.html) - Popular launcher, but requires purchase.

### Documentation

Reading reference materials and documentation is critical to understanding a lot
of technologies we will be learning in this course. Rather than having to
_google_ constantly, and click through the various results, it is often faster
and more efficient to keep necessary documentation handy and go straight to the
source to try and find an answer.

The tools listed below help us with this. They act as a single location to house
documentation for the different languages and frameworks we'll be learning, making
the docs easier to search as well as available offline.

[Dash](http://kapeli.com/dash) - Dash is a comprehensive documentation tool that
includes downloadable docs. Dash's full version costs money, but the application
is free to try with no limitations.

[DevDocs](http://devdocs.io/) - A free Dash alternative built in the browser.

### Git Visualizers

Understanding and visualizing Git can be difficult, especially when only dealing
with the command line interface. Below are some tools that are designed to bring
more visualization to Git repositories, which can help when dealing with more
complex git history-related issues.

[Github OS X](https://desktop.github.com/) - GitHub's official Desktop application

[SourceTree](http://www.sourcetreeapp.com/) - Free Git GUI that includes additional tutorials and git history visuals

[Git Kraken](https://www.gitkraken.com/) - A comprehensive Git client that includes
a text editor and git history visuals. Some features require 

### Window Management

You will often find yourself flipping between a text editor, browser and
terminal. Being able to manage application windows can help keep your workflow
efficient and less frustrating. Below are some tools that help manage
application windows:

[Spectacle](http://spectacleapp.com/) - Free and open source.
[Breeze](http://www.autumnapps.com/breeze/) - Demo available for download; full application available for purchase.

### Programming Fonts

You're going to be spending a ton of time staring at your screen. The default
fonts you have installed probably aren't the most readable. Here are some nice
ones you may want to consider installing:

- [Flatiron Collection of Fonts](http://flatiron-school.s3.amazonaws.com/resources/programming%20fonts.zip)
- [Dan Benjamin's Top 10 Programming Fonts](http://hivelogic.com/articles/top-10-programming-fonts/)
- [Dan Benjamin on Anonymous Pro](http://hivelogic.com/articles/anonymous-pro-programming-monospace-font)
- [Jeff Atwood on Programming Fonts](http://www.codinghorror.com/blog/2007/10/revisiting-programming-fonts.html)
- [Managing Fonts in OS X](http://support.apple.com/kb/ht2435)

[Heroku](https://www.heroku.com/)

