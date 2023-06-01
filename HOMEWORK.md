# Volatility Memory Dump Analysis Homework

- Using the provided memory dump, use the output of Volatility's plugins to get the answers to the following questions:
	- The memory dump file is extremely large, so instead of downloading the file and setting up Volatility, you have the option of using the preloaded outputs in `/resources`
	- If you do choose to use the actual memory dump, make sure to clone Volatility and store the `vmlinux-5.19.0-42-generic.json` file in `volatility3/volatility/symbols/linux/`.  If the `linux` directory does not exist, create it and add the file.

- Q1) What version of Linux was running on this machine?
- Q2) What process was running under PID 44252?
- Q3) Where did the user ssh into?
- Q4) What browser was open, and what was the parent process of this program?
- Q5) What file did the user download from the internet?
- Q6) What was the value of the `XDG_SESSION_TYPE` environment variable?

Please also state which plugins you used to find each answer.
