# build
An alternative to make

### Installation:
Install python onto your system and type `pip install argparse` and `pip install tqdm`

Download the binary from here and send it to `/bin` (linux) or `C:\Windows\System32` (windows). 

For linux you also need to type `chmod +x /bin/build`

### Usage:
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
# As you've seen, you can make comments with #
```
