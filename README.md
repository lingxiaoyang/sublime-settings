# Sublime Text Settings for Converted Emacs User

Steps to follow:

1. Clone the repo:

   On mac:
   
   `git clone git@github.com:lingxiaoyang/sublimemacs-settings.git ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/User`

   On cygwin: 
   
   `git clone git@github.com:lingxiaoyang/sublimemacs-settings.git /cygdrive/c/Users/$USER/AppData/Roaming/Sublime\ Text\ 3/Packages/User`

2. Install Package Control. The packages will pop in automatically.

3. Create fake `emacs` command:

   On mac: create `/usr/local/bin/emacs` as follows and set executable.
   
   ```bash
   #!/bin/bash
   /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl -n "$@"
   ```
   
   On cygwin: create `/usr/local/bin/emacs` as follows and set executable.
   
   ```bash
   #!/bin/bash
   new_args=()

   for ARG in "$@"; do
     if [[ $ARG == -* ]]; then
       NEW_ARG="$ARG"
     else
       NEW_ARG=$(cygpath --windows "$ARG")
     fi
     new_args+=("$NEW_ARG")
   done

   /cygdrive/c/Program\ Files/Sublime\ Text\ 3/subl.exe -n "${new_args[@]}"
   ```
   
4. Set up default editor: add following line to `~/.bashrc` or `~/.bash_profile`:

   ```
   export EDITOR="emacs -w"
   ```
   
Welcome to SublimEmacs!
