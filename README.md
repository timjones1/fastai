# Fast.ai - Deep Learning for coders 2022 with University of Queensland

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
-  `cd /` change to root directory
-  `pushd` followed by a directory to change to that directory with memory of current location, `popd` to return to location in memory.

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

### Walkthru 5

learning vim, definitely an intimidating text editor but Jeremy uses it with ease and shows why it is powerful despite having a steep learning curve and so many keyboard shortcuts:

- `:q!` quit without saving. `:` enters EX mode, `q` is quit. `!` says i am sure and supresses any dialogue about closing without saving.
- `:wq` write and quite. `:w` writes all changes to file. `:w filename` will write to a file named `filename`. adding the `q` quits after saving.
- `i` enter insert mode, one of the edit modes for vim, if we are not in an edit mode we cannot alter the text in a document.
- `Esc` exit insert mode or EX mode, and return to command mode.
- `u` Undo
- `Ctrl + Z` put vim into background mode.
- Use `fg` in the terminal to bring vim back into the foreground.
- Use `jobs` to see processes running in the background.

- `o` open new line of text below current cursor position and enter insert mode, ready for text entry.
- `Shift + o` open a new line of text above the current curor position.
- `Shift + a` append current line by moving cursor to end of line and enteirng insert mode.
- `x` cross out (delete) character when in insert mode

#### Motions
- `w` to move forwards one word
- `b` to move backwards by one word
- `j` move down one line or use curor down arrow
- `k` move up one line or use cursor up arrow
- `h` move left one chracter or use left arrow
- `l` move right one character or use right arrow
-  `Shift + }` move to begining of next paragraph

motions can be repeated multiple times and combined with commands which is where we start to see some of the power of vim.

- `2w` moves forwards 2 words.
- `4j` moves down 4 lines

#### Walkthru 6 aka Live Coding session 6.

### Live Coding 7

`scp` to copy files over ssh to a remote machine, scp = Secure Copy over SSH. `rsync` is the newer way to copy incrementally `scp` has been officially deprecated.

Shortcuts can be created for use inside the linux terminal to reference remote servers using the file `.ssh/config` , set `Host Local` and then this can be referenced as `:local` from the terminal.

```Host Local
    Hostname 192.168.0.20  #  ip address of GPU server
    User timjones1
    LocalForward 8889 127.0.0.1:8888 # port forwarding settings
```
    
Piping commands in the terminal using the `|` command

`ls train_images | head`  can be used to pipe the contents of a directory to the head command and we will only have the top 10 lines returned.

`ls train_images | wc -l` for counting the number of files, wc stands for word count, but we need to add -l to count the number of lines.

`ls train_images | tail` to view the final records in the folder.

These pipiong commands can be used on .csv files as well to view the first/last records, count the number of records or to search for results by piping to the `grep` command.

`cat train.csv | head` will pipe the contents of the train.csv file to head which will only access the first 10 by default.

`cat train.csv | grep ADT45` to find instances of this text in the contents of the file.

### Live Coding 8

forwarding ports in linux so that we can use jupyterlab from a remote machine when connecting via ssh. we can set up ssh forwarding and an alias for other machines in a `config` file in our `.ssh` folder

```
Host local
 Hostname 192.168.1.101
 User timjo
 LocalForward 8888 127.0.0.1:8888
 ```
 
 so now we can use the command localhost:8888 to access the the jupyter server running on our local GPU machine 






 


