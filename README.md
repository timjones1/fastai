# Fast.ai
Base for notes and code as part of fast.ai Deep Learning for Coders V5 live course with University of Queensland.

### Lessons 1 & 2
Created a basic classifier with Fast.ai and then got it running online using Gradio and Higging face spaces. 

https://huggingface.co/spaces/Timjo88/storm_damaged_house


### Walkthru 1
setting up environments on your own machine

- start with clean ubuntu installation
- install mamba-forge from : https://github.com/conda-forge/miniforge#mambaforge using wget
- build up scripts to create desired environment such as jeremy's `setup-conda.sh` available here: https://github.com/fastai/fastsetup

if we want to run downloaded scripts we will need to alter permissions as by default execution of files is disabled, we will need to use the `Chmod` program with the following flag:

`chmod -u+x setup-conda.sh`

- `u`               for current user
 -`+`               add permission
- `x `              for executing files
- `setup-conda.sh`  to this file

once permissions have been updated we can executed the downloaded sh script file.

Other shortcuts in linux:

- `Ctrl + r` : search `.bash_history` for matching commands, `del` to clear, `esc` to close. Jeremy copies and pastes from `.bash_history` to create scripts. 
- `Ctrl + l` : clear terminal screen
- `Ctrl + u` : Clear line
- `Ctrl + e` : move to start of line
- `Ctrl + a` : move to end of line
-  `cd` to change to home directory
-  `cd /

`!!` run last command
`!` followed by some text will run last command matching that text

Aliases can be very handy

`alias jl = "jupyter lab"`

Aliases will not be automatically be saved when you reopen your terminal, so if you want these aliases to persist then add them to your `.bashrc` file, which is run everytime you open your terminal.

I often use notepad++ to open large text files in windows and by adding the below alias to my `.bashrc` I can now use this editor from within the ubuntu terminal, i also had to add this file path to my system environment variables for it to work:

`alias npp="/mnt/c/Program\ Files\ \(x86\)/Notepad++/Notepad++.exe"`

I have been using nano in ubuntu which i prefer to vim for ease of use but I also like how easy it is to edit text in my traditional windows editor with the above alias as well.

### Walkthru 3

working with drives in linux, with Paperspace they provide a drive with persistent storage in the `/storage` folder, to check the drives and space available use `df` which stands for disk free, use `df -h` for human readable space free.

symlinks are very handy ways of making shortcuts between directories. they can be created using `ln -s` command. In the walkthru, Jeremy makes symlinks between the persistent storage area provided by Paperspace and the temporary directories where we are working on the servers, so we can retain the installed package state different server instances. 


### Walkthru 4

while working on the terminal if you want to delete everything to the left of the cursor position it is `Ctrl + U` , to delete everything to the right of the cursor it is `Ctrl + K`.

if we want to use the final arguement of the previous line of a terminal command in our current command we can reference it using `!$`

for example `mkdir /storage/cfg`
now we can reference the arguement `/storage/cfg` in a new commmand for example `mv .local/ !$` which will move the `.local` folder to the `/storage/cfg` location


