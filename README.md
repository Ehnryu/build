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
@python def hello_world(args=None):||?|?print("hi")|| print("hola")||hello_world()
# you can get the arguments given comma seperated by:
echo "*getargs"
# this only works if the "--sendargs" flag is used.
```
