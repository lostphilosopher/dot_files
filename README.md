# dot_files

`bash_profiles` and `vimrc` managment for assorted linux, mac, and windows machines.

## Installation

1. Move to your home directory `cd ~`  
2. Get a copy of this repository `git clone https://github.com/lostphilosopher/dot_files.git` 

## bash

This section applies to the code found under [dot_files/bash/](https://github.com/lostphilosopher/dot_files/tree/master/bash).

### Set Up

1. Copy the dot_files bash_profile file to your home directory `cp ~/dot_files/bash/bash_profile ~/.bash_profile`  
2. Create a .manifest file inside dot_files/bash/ `touch ~/dot_files/bash/.manifest`  
3. Open the .manifest file and indicate which modules you would like to load (look [here](https://github.com/lostphilosopher/dot_files/tree/master/bash/lib) to see available modules) including a module is as easy as `[ -r ~/dot_files/bash/lib/git ] && source ~/dot_files/bash/lib/git`  
4. Create a .private file inside dot_files/bash/ to hold any secure data your scripts might need `touch ~/dot_files/bash/.manifest`
5. Save your .manifest file and source your ~/.bash_profile `source ~/.bash_profile`
6. In your terminal you should see something like:  
```
Sourcing .manifest ...  
Sourcing git preferences...  
Sourcing grep preferences...  
Sourcing Heroku preferences...  
Sourcing ruby preferences...  
Sourcing Vagrant preferences...
``` 

### Further Configuration

**Managing a new tool:**   
If you find a new tool / project / consideration you'd like to manage with this system you can add an appropriate file to the lib/ directory. The convention is to begin each file with:
```bash
# NAME_OF_THING_THIS_MODULE_MANAGES
domain=NAME_OF_THING_THIS_MODULE_MANAGES
format_sourcing_message
```
([example](https://github.com/lostphilosopher/dot_files/blob/master/bash/lib/git#L1-L3))  
Then you'll need to add this file to your .manifest and source your ~/.bash_profile again.

**Using the "self managaged" tools:**    
The repo has some meta tooling in it that lets it manage itself (After the initial Set Up has been completed.) The code for this can be found [here](https://github.com/lostphilosopher/dot_files/blob/master/bash/lib/self_managed). This provides 3 meta utilities:  
- `bashedit`/`editbash`: Open dot_files/bash/bash_profile in vim for fast editting.  
- `rebash`: Copy dot_files/bash/bash_profile to ~/.bash_profile and source ~/.bash_profile.  
- `commitdots`: Update your local master branch and commit your local changes to origin master.  

## Vim

This section applies to the code found under [dot_files/vim/](https://github.com/lostphilosopher/dot_files/tree/master/vim).

### Set Up 

1. Copy the vimrc file to the appropriate directory `cp ~/dot_files/vim/vimrc ~/.vimrc`  
2. Follow the [instructions in vimrc](https://github.com/lostphilosopher/dot_files/blob/master/vim/vimrc#L4-L8)

### Further Configuration

If you are using the bash configuation above in conjunction with this vim configuration the following meta utilities are available [here](https://github.com/lostphilosopher/dot_files/blob/master/bash/lib/vim) and [here](https://github.com/lostphilosopher/dot_files/blob/master/bash/lib/self_managed):  
- `vimedit`/`editvim`: Open the dot_files vimrc file for easy editting.  
- `revim`: Copy ~/dot_files/vim/vimrc to ~/.vimrc.
- `commitdots`: Update your local master branch and commit your local changes to origin master.

## Notes

- I recommend https://github.com/stephenway/monokai.terminal for the terminal profile.  
