# This document is required.

## How to download Volatility for Linux, Windows, and Mac:
- Head over to this github repo and clone the repository
```git clone git@github.com:volatilityfoundation/volatility3.git```
- The most current version of volatility requires Python 3.7.0 or later
- You can download the latest Python version from the web and the necessary dependancies with the following command: 
```pip3 install -r requirements-minimal.txt```
- cd into the volatility3 directory
- You can now run volatility3 commands using ```python3 vol.py COMMAND```
- You can see the possible commands to run with volatality using the -h flag: ```python3 vol.py -h```
- Note: You may want to create an alias to this program for ease of access by adding this to your .bashrc/.profile: 
```alias volatility='python3 path/to/directory/vol.py'```

## How to perform volatile memory acquisition

### Linux
- We'll use a program called AVML to create a memory image
- Run this command: ```wget https://github.com/microsoft/avml/releases/download/v0.11.2/avml``` to download the program```
- To make it executable, run ```chmod a+x path/to/avml```
- To use the program, simply run ```avml <FILENAME>``` to a acquire a memory image and dump it to a file
- Now we are ready to analyze this image using Volatility

### Windows
- We'll be using a program called DumpIt.exe

### MacOS
