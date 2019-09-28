# Sublime Text Settings for Converted Emacs Users

Steps to follow:

1. Clone the repo:

   On mac:
   
   `git clone git@github.com:lingxiaoyang/sublime-settings.git ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`

   On cygwin: 
   
   `git clone git@github.com:lingxiaoyang/sublime-settings.git /cygdrive/c/Users/$USER/AppData/Roaming/Sublime\ Text\ 3/Packages/User`

2. Install Package Control. The packages will pop in automatically.

3. Create fake `emacs` command:

   On mac:
   
   On cygwin: create `/usr/local/bin/emacs` as follows and set executable.
   
   ```bash
   #!/bin/bash
   /cygdrive/c/Program\ Files/Sublime\ Text\ 3/subl.exe -n -w $(cygpath --windows $1)
   ```
   
4. Add to `~/.bashrc` or `~/.bash_profile`:

   ```
   export EDITOR="emcacs"
   ```
   
Welcome to SublimEmacs!
