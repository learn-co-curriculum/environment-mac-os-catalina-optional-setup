# Optional Installation Instructions

## Introduction

The tools in this lesson are not specifically required, but they are things we
recommend based on previous student experiences. Feel free to pick and choose
what you would like to use and install.

### Customizing Your Terminal Prompt

When writing a command in the terminal, everything to the left of your command
is referred to as your terminal's _prompt_. At the moment, your prompt may include
something like your username for the computer. You can customize this to include many
helpful things such as the current time and the directory you are in.

In the previous setup instructions, the `~/.zprofile` dotfile was updated to
include some helpful shortcuts. Included in that file is a way to change your prompt,
but it is currently commented out.

Open `~/.zprofile` in your text editor. Near the beginning of the file, you
should see the following:

```sh
  # ## This function builds your prompt. It is called below
  # function prompt {
  #   ## Define the prompt character
  #   local   CHAR="♥"
  
  #   ## Define some local colors
  #   local   RED="\[\e[0;31m\]"
  #   local   BLUE="\[\e[0;34m\]"
  #   local   GREEN="\[\e[0;32m\]"
  #   local   GRAY_TEXT_BLUE_BACKGROUND="\[\e[37;44;1m\]"
  
  #   ## Define a variable to reset the text color
  #   local   RESET="\[\e[0m\]"
  
  #   ## ♥ ☆ - Keeping some cool ASCII Characters for reference

  #   autoload -U colors && colors

  #   ## Here is where we actually export the PS1 Variable which stores the text for your prompt
  #   PS1="%{$fg[cyan]%}%(4~|%-1~/.../%2~|%~) %{$reset_color%}%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}♥ > %{$reset_color%}% "
  #   PS2='> '
  #   PS4='+ '

  #   ## Additional Option: Minimal // ♥ > Prompt
  #   # PS1="%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}♥ > %{$reset_color%}%  "
  #   #   PS2='> '
  #   #   PS4='+ '

  # }

  # ## Finally call the function and our prompt is all pretty
  # prompt
  ```

  Remove **just the first #** from each line to uncomment this section (in VS Code,
  you can do this by highlighting the entire section and pressing ⌘/ (command
  and forward slash). This will comment or uncomment whatever is highlighted.

  The result should look like this:

  ```sh
  ## This function builds your prompt. It is called below
  function prompt {
    ## Define the prompt character
    local   CHAR="♥"
  
    ## Define some local colors
    local   RED="\[\e[0;31m\]"
    local   BLUE="\[\e[0;34m\]"
    local   GREEN="\[\e[0;32m\]"
    local   GRAY_TEXT_BLUE_BACKGROUND="\[\e[37;44;1m\]"
  
    ## Define a variable to reset the text color
    local   RESET="\[\e[0m\]"
  
    ## ♥ ☆ - Keeping some cool ASCII Characters for reference

    autoload -U colors && colors

    ## Here is where we actually export the PS1 Variable which stores the text for your prompt
    PS1="%{$fg[cyan]%}%(4~|%-1~/.../%2~|%~) %{$reset_color%}%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}♥ > %{$reset_color%}% "
    PS2='> '
    PS4='+ '

    ## Additional Option: Minimal // ♥ > Prompt
    # PS1="%{$fg[blue]%}// %{$reset_color%}% %{$fg[red]%}♥ > %{$reset_color%}%  "
    #   PS2='> '
    #   PS4='+ '

  }

  ## Finally call the function and our prompt is all pretty
  prompt
  ```

  Save `~/.zprofile` and in your terminal, run the following command:

  ```sh
  source ~/.zprofile
  ```

  You should see your prompt change to display the current dirrectory, followed by `// ♥ >`.

  > **Note:** An alternative, minimal prompt (just `// ♥ >`)is also provided. If you
  > would like to use this second prompt, comment out the lines that start with
  > `PS1`, `PS2`, and `PS4`. Just below these are the alternative assignments.
  > Uncomment these and rerun `source ~/.zprofile` to see the change.

### Key Repeat

Turn up your key repeat. Open System Preferences by clicking the apple icon in
the top left corner of your screen and selecting System Preferences. Then Click
Keyboard and make sure both Key Repeat and Delay Until Repeat are turned up all
the way. This will allow you to move your cursor through text much faster.

### Install DB Browser for SQLite

Install the DB Browser for SQLite at https://sqlitebrowser.org/

This tool helps you visualize and interact with database tables, which will be
helpful as you learn SQL.

### Install Postgres

The default database that Rails uses is SQLite but you may find you need other
database management systems as you build out and deploy projects. One common
relational database management system is PostgreSQL. PostgreSQL is necessary in
certain situations (such as deploying to Rails applications to the free hosting
service [Heroku][]).

To install Postgres, run the following three commands:

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
