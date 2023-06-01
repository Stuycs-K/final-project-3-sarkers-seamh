## INTRO

Volatility is a memory forensics tool that is used to extract information from memory images (memory dumps) of different OS systems.

It is the most widely used framework to extract digital artifacts and information from volatile memory or RAM.

Some uses of Volatility include listing running processes, closed/open networks, internet history, hashed passwords, and retrieving commands entered into the terminal.


## NOTES

- A memory image is a programming pattern in which data stored in the database resides in the memory → more simply it is a copy/snapshot of a machines virtual memory saved to a file for easier analysis and viewing

- Volatility uses multiple plugins to extract information from a memory dump

- Before analysis you must identify the type of memory dump image

- Extracting the memory itself can be performed in a variety of ways and using multiple tools which most often output a .raw file

- To see the possible plugins use the help menu of volatility ```python3 vol.py -h```

- To use plugin follow format ```python3 vol.py -f <FILENAME> <OSname>.<PLUGINname>```


## DICT

- DLLs or dynamically linked library is a collection of small programs that large programs can load and can be used spontaneously by many


## EXAMPLE PLUGINS

| Plugin        | Description   |
| ------------- | ------------- |
| **info**      | information about the host running the memory dump |
| **pslist**    | will return the list of processes running from a doubly linked list that tracks processes from the memory; similar to the process list in task manager |
| **psscan**    | another way to identify running processes but by finding data structures that match ```E_PROCESS```; can help against malware evasion measures |
| **pstree**    | another way to identify processes using parent process id; provides a more fuller description of processes during extraction |
| **netstat**   | identifies all memory structures with a network connection |
| **dlllist**   | lists all the DLLs associated with processes at the time of extraction |
| **malfind**   | identifies any injected processes and their PIDs along with their offset address; works by scanning heaps and identifying processes with the executable bit set RWE or RX |
| **hashdump**  | extracts all the username and password hashes from the machine |



## OUR OWN PLUGIN
```python
import volatility.plugins.common as common

class TestPlugin(common.AbstractWindowsCommand):
  def render_text(self, outfd, data):
    outfd.write("hi\n")
```


## OTHER RESOURCES
- [Official Website for Volatility](https://www.volatilityfoundation.org/)

- [Volatility Docs](https://volatility3.readthedocs.io/en/latest/index.html)

- [List of commands cheatsheet](https://book.hacktricks.xyz/generic-methodologies-and-resources/basic-forensic-methodology/memory-dump-analysis/volatility-cheatsheet)

- [Youtube Tutorial on Volatility](https://www.youtube.com/watch?v=Uk3DEgY5Ue8)

- [Resource Docs](https://volatility3.readthedocs.io/en/latest/basics.html)
