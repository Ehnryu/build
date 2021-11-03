# build
An alternative to make

### Installation:
Install python onto your system and type `pip install argparse` and `pip install tqdm`

Download the binary from here and send it to `/bin` (linux) or `C:\Windows\System32` (windows). 

For linux you also need to type `chmod +x /bin/build`

### Usage:
To run Buildfile simply type `build --build`

To run a specified function type `build -r <function>`

Create a file called `Buildfile` (caps matters)
and input the following:
```
func hello_world:
# you can use bash in the Buildfile:
echo "hi"
# you can perform silent commands
@q touch hi
# you can use python:
@python 1 + 1
# you can use python functions
# || is return aka \n
# |?| is tab
@python def hello_world(args=None):||?|?print("hi")||?|?print("hola")||hello_world()
# you can get the arguments given comma seperated by:
echo "*getargs"
# this only works if the "--sendargs" flag is used.
# you can get the system platform by:
echo "*getplatform"
# you can download files too
@dl url:https://google.com/index.html opt:index.html
# url and output
# you can check for required OS and unsupported OS
@uOS win32,win64
@reqOS darwin64
# Seperate multiple OS's by commas
# you can add packages, so far only supporting python, javascript and debian packages
# LANG ALIASES
# python - py, python
# javascript - js, javascript
# debian - apt, deb
# BASIC EXAMPLE
@addpkg lang:py pkg:pip
# ADVANCED EXAMPLE
# pm: allows you to pick the package manager
@addpkg pkg:express pm:npm
# ADVANCED EXAMPLE 2
@addpkg pkg:pip lang:py flags:--upgrade/-v
# seperate flags with /
# you can also not print the contents of the line
@dp echo "not printing contents so you can only see this"
# you can copy files
@cp src:tocopy.txt dest:../tocopy.txt
# you can move files
@mv src:tocopy.txt dest:movedfile.txt
# you can rename files
@rename src:tocopy.txt target:renamedfile.txt
# you can delete files
@delf target:todelete.txt
# you can delete folders
@deld target:toremove
# you can create files
@create name:tocreate.txt
# As you've seen, you can make comments with #
# While not needed for --build this is needed to run specific functions:
\endfunc
func run_me_only:
echo "You ran me only"
\endfunc
# type "build -r run_me_only <args>" to only run that function
```
