# System Call Overview

A system call is a way for user-space code to call a function in the kernel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-11-02%20071933.png)

* Applications call functions in libraries (*Std C Lib*), which some of them invoke kernel system calls
* System calls may interact with hardware (*An application may interact with a disk by performing read and write operations*)
