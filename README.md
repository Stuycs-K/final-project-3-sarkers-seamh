# Memory Forensics Using Volatility

## TNPG: 
- Members: Hamim Seam and Samin Sarker

## Project Description
Volatility: A command line memory analysis and forensics tool that extracts info from memory dumps
 - supported by Windows, MAC, and Linux systems

The goal of our lesson is to introduce Volatility3 as a tool to analyze memory images for process and system information through its various plugins.
In class we will demo a windows memory dump, and for homework students will analyze a Linux memory dump.

- Links to the [presentation](https://github.com/Stuycs-K/final-project-3-sarkers-seamh/blob/main/PRESENTATION.md) and [homework](https://github.com/Stuycs-K/final-project-3-sarkers-seamh/blob/main/HOMEWORK.md)

## Installation

### How to download Volatility for Linux, Windows, and Mac:
- Head over to this github repo and clone the repository
```git clone git@github.com:volatilityfoundation/volatility3.git```
- The most current version of volatility requires Python 3.7.0 or later
- cd into the top level directory
- You can download the latest Python version from the web and the necessary dependancies with the following command: 
```pip3 install -r requirements-minimal.txt```

### How to perform volatile memory acquisition
- Linux
  - We'll use a program called AVML to create a memory image
  - Run this command: `wget https://github.com/microsoft/avml/releases/download/v0.11.2/avml` to download the program
  - To make it executable, run `chmod u+x path/to/avml`
  - To use the program, simply run `avml <FILENAME>` to a acquire a memory image and dump it to a file
  - Now we are ready to analyze this image using Volatility

- Windows
  - Run FTK Imager as an adminstrator
  - In the "File" menu on the top right, select "Capture Memory"
  - Choose a destination folder/filename
  - Select "Capture memory" and wait for the memory image to generate

- MacOS
  - You can use OSXPMem to acquire the memory dump
  - Run the following: `wget https://github.com/google/rekall/releases/download/1.7.2rc1/rekall-OSX-1.7.2rc1.zip`
  - Then unzip the file by running `unzip rekall-OSX-1.7.2rc1.zip`
  - To use the program, run `./osxpmem.app/osxpmem -o <output_dir>`
  - Now we can analyze the memory dump

- Note that although it is good to know how to acquire memory dumps to use with Volatility, the homework will NOT require you to do so.

## Usage
- Before analyzing a memory dump, you must have the matching symbol table stored in `volatility3/volatility3/plugins`
  - The way to acquire the symbol table for a system varies across different operating systems and even versions
  - If you were to run Ubuntu 22.04, we have a symbol table for that in the `/resources` directory

- In the top level `volatility3` directory, run the following: `python3 vol.py -f <memory image file> <OS>.<plugin>`
  - Run with `sudo` if needed
  - Example: `sudo python3 vol.py -f memory.dmp linux.pslist`
  - Note: the `isfinfo` and `banners` plugins do not need an OS prepended to it

- For a list of commands: `python3 vol.py -h`
