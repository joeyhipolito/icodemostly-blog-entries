### Previously
On [Configurations Part 1 of 2](my-devt-workflow-part-3-configurations), I go over on having a bash terminal on your windows machine and I talked about some concepts in bash configuration. Now lets dive in right into the nitty gritty part of this configuration walk through.

### The Nitty-Gritty
We'll start by creating a file named `.bash_profile` using our favorite text editor, mine is [Sublime Text 3](http://sublimetext.com/3).

####Aliases
Aliases are your shortcuts or commands that help you execute cli commands. This is common when you have to execute lengthy commands because it needs a lot of complex arguments.

*in your .bash_profile*

    # After hashes are comments
    # : Traversing Folders
    alias ..='cd ..'
    alias ...='cd ../..'
    alias ....='cd ../../..'
    alias .....='cd ../../../..'
    
    # : Applications
    alias subl='C:\Program Files\Sublime Text 3\sublime_text.exe '
    alias v='vim '
    alias vi='vim '
    
    # : Directory Listing
    alias l='ls -lF --color'
    alias ls='ls -a --color'
    # list dotfiles too
    alias la='ls -laF --color'
    alias lsa='ls -la --color'

**To make it work**
To make it work you need to tell your shell to use the `.bash_profile` as a `source` of configuration, by doing this

    $ source ~/.bash_profile


I guess what you see is what you get, you can have it your way, or just copy mine! At that point you are I assume can remember some of the commands, you've made it anyway.

You are now ready to append more stuff into your `.bash_profile`. There are thousands of dotfiles all over the internet, and I am gave you already a hint of what needs to be in there.

### Eventually
Eventually you'll separate your config files like so

* .aliases
* .bash_prompt
* .bash_profile
* .functions

### References
There are tons of resources about dotfiles and most are found in github, I would also want to point you to my [ubuntu dotfiles](https://github.com/joeyhipolito/dotfiles).

### In the end
If you find yourself wanting more, you will probably end up having a shell that looks like this one:

{<1>}![Customized the prompt. Colors.](/content/images/2014/Mar/custom_prompt_shell_JPG.jpg)