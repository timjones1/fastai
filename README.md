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

chmod -u+x setup-conda.sh

u -             for current user
+               add permission
x               for executing files
setup-conda.sh  to this file

once permissions have been updated we can executed the downloaded sh script file.

