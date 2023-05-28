## WRITEUP
- Volatility is a memory forensics tool that is used to analyze memory dumps
- It is the most widely used framework to extract digital artifacts and information from volatile memory or RAM
- Some uses of Volatility include listing running processes, closed/open networks, internet history, hashed passwords, and retrieving commands entered into the terminal

## GETTING STARTED
### How to download Volatility for Linux, Windows, and Mac:
- Head over to this github repo and clone the repository
```git clone git@github.com:volatilityfoundation/volatility3.git```
- The most current version of volatility requires Python 3.7.0 or later
- You can download the latest Python version from the web and the necessary dependancies with the following command: 
```pip3 install -r requirements-minimal.txt```
- cd into the volatility3 directory
- You can now run volatility3 commands using ```python3 vol.py COMMAND```
- You can see the possible commands to run with volatality using the -h flag: ```python3 vol.py -h```
- **Note**: You may want to create an alias to this program for ease of access by adding this to your .bashrc/.profile: 
```alias volatility='python3 path/to/directory/vol.py'```
- **Alternatively**: You can use the volatility preinstalled in the volatility tryhackme room

### How to perform volatile memory acquisition
- Linux
  - We'll use a program called AVML to create a memory image
  - Run this command: ```wget https://github.com/microsoft/avml/releases/download/v0.11.2/avml``` to download the program```
  - To make it executable, run ```chmod a+x path/to/avml```
  - To use the program, simply run ```avml <FILENAME>``` to a acquire a memory image and dump it to a file
  - Now we are ready to analyze this image using Volatility

- Windows
  - We'll be using a program called DumpIt.exe

- MacOS
  - Working on this...

### C Program to generate memory dumps on a machine
```C
void memoryDump() 
{
 
}
```

## NOTES
- A memory image is a programming pattern in which data stored in the database resides in the memory → more simply it is a copy/snapshot of a machines virtual memory saved to a file for easier analysis and viewing
- Volatility uses multiple plugins to extract information from a memory dump
- Before analysis you must identify the type of memory dump image
- Extracting the memory itself can be performed in a variety of ways and using multiple tools which most often output a .raw file

- When using a plugin you must specify the OS type
  - .windows
  - .mac
  - .linux
- In the case you don’t know the OS or image type of the memory dump you can use the ```imageinfo``` plugin, which assigns the best possible OS profile to the memory file

- To see the possible plugins use the help menu of volatility ```python3 vol.py -h```
- To use plugin follow format ```python3 vol.py -f ‘FILENAME’ imagetype/OSname.PLUGINname```

## PLUGINS
- **info**: information about the host running the memory dump
  - Format: ```python3 vol.py -f <file> windows.info```
 
- **pslist**: will return the list of processes running from a doubly linked list that tracks processes from the memory; similar to the process list in task manager
  - Format: ```python3 vol.py -f <file> windows.pslist```
 
- **pscan**: another way to identify running processes but by finding data structures that match ```E_PROCESS```; can help against malware evasion measures
  - Format: ```python3 vol.py -f <file> windows.psscan```
 
- **pstree**: another way to identify processes using parent process id; provides a more fuller description of processes during extraction
  - Format: ```python3 vol.py -f <file> windows.pstree```
 
- **netstat**: identifies all memory structures with a network connection
  - Format: ```python3 vol.py -f <file> windows.netstat```
 
- **dlllist**: lists all the DLLs associated with processes at the time of extraction
  - DLLs or dynamically linked library is a collection of small programs that large programs can load and can be used spontaneously by many
  - Format: ```python3 vol.py -f <file> windows.dlllist```
 
- **malfind**: identifies any injected processes and their PIDs along with their offset address; works by scanning heaps and identifying processes with the executable bit set RWE or RX
  - Format: ```python3 vol.py -f <file> windows.malfind```

## OTHER RESOURCES
- [Official Website for Volatility](https://www.volatilityfoundation.org/)
- [List of commands cheatsheet](https://book.hacktricks.xyz/generic-methodologies-and-resources/basic-forensic-methodology/memory-dump-analysis/volatility-cheatsheet)
- [Quick Reference Cheatsheet #2](https://downloads.volatilityfoundation.org/releases/2.4/CheatSheet_v2.4.pdf)
	- Note: though an easy reference, this file is made for Volatility 2, so some features may not be included yet
