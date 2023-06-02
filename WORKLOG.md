# Work Log


## Member 1: SAMIN SARKER


## 05-17-2023
- Created repository and added group project description to READ.md; started planning lesson


## 05-18-2023
- Worked on Tryhackme room to learn Volatility in addition to online videos and websites teaching the tool


## 05-19-2023
- Absent due to AP testing


## 05-20-2023
- Started a [google doc](https://docs.google.com/document/d/1LjZducwntw_FBgmiHJieqnYrJdgJ6loLmlshRz0lo3U/edit?usp=sharing) to organize information to be included in presentation; reviwed how to write/edit .md files


## 05-21-2023
- Continued to work on google doc adding more information; tested different volatility plugins


## 05-22-2023
- Added directions to download volatility by cloning repository and re-organized the group work log


## 05-23-2023
- Finalized google doc and information to be included in repository with Hamim


## 05-24-2023
- Helped Hamim research other topics/capacities to add to presentation


## 05-25-2023
- Continued to learn Volatility via online videos and websites; specifically password and username plugin hashing


## 05-26-2023
- Tested memory dump tool on linux machines through ssh; Tested mac memory dump tool on own machine


## 05-27-2023
- Updated presentation with more notes and began researching a C program to create memory dumps


## 05-28-2023
- Worked on building a C program to extract RAM memory and updated presentation with more web resources and plugins


## 05-29-2023
- Designed python code for kernal memory dumps on mac and windows in .raw or .vmem file format


## 05-30-2023
- Researched how to make volatility plugins; followed tutorial and started creating program


## 05-31-2023
- Tested memory dumps on linux computers at school; went over presentation organization and design with partner


## 06-01-2023
- Finished creating our own plugin with python; reorganized presentation with tables and more meta info



## Member 2: HAMIM SEAM


## 05-17-2023
- Started planning specifics with Samin


## 05-18-2023
- Worked on TryhackMe room for Volatility and watched videos on youtube covering the tool


## 05-19-2023
- Absent due to AP testing


## 05-20-2023
- Helped add notes and organize presentation in the google doc


## 05-21-2023
- Added more information to google doc and a list of resources


## 05-23-2023
- Helped Samin finalize information on google doc and what would be included in the actual presentation


## 05-24-2023
- Researched different levels of added complexity for project: website, personal plugin, memory dump tool


### 05-25-2023
- Updated instructions to include memory acquisition using AVML (for Linux machines)


## 05-26-2023
- Researching LiME and testing AVML for memory acquisition of Linux machines


## 05-27-2023
- Researching Volatility libraries and symbol tables


## 05-28-2023
- Setup a virtual machine using VMWare to generate memory dumps compatible with Volatility\
  - Although AVML can generate memory dumps from WSL, they may not be compatible with Volatility
- Updated homework directions; the memory dump will be generated/customized using the VMWare virtual machine


## 05-29-2023
- Configured the required JSON symbol table file to analyze the memory dump for homework (now in `/resources`)


## 05-30-2023
- Changed homework to not need the actual memory dump (working off plugin outputs in txt files)


## 05-31-2023
- Tested memory dumps on linux computers at school; went over presentation organization and design with partner


## 06-01-2023
- Updated presentation and README to match required info



## References and Resources
> general info
- https://volatility3.readthedocs.io/en/latest/
- https://dfir.science/2022/02/Introduction-to-Memory-Forensics-with-Volatility-3
- https://www.osforensics.com/tools/volatility-workbench.html
- https://newtonpaul.com/malware-analysis-memory-forensics-with-volatility-3/
- https://www.varonis.com/blog/how-to-use-volatility
- https://www.hackthebox.com/blog/memory-forensics-volatility-write-up

> youtube videos
- https://www.youtube.com/watch?v=Uk3DEgY5Ue8
- https://www.youtube.com/watch?v=s_D_XBgawUo
- https://www.youtube.com/watch?v=utDjrceyy00

> info about plugins
- https://volatility3.readthedocs.io/en/latest/simple-plugin.html
- https://reversea.me/index.php/writing-a-volatility-3-plugin/
- https://github.com/volatilityfoundation/community3
