## ASSIGNMENT 2 ##
**BASH SCRIPTING EXERCISES**
## Question 1 ##
1. How many processes are currently running on your system? Use ps and wc, the first line of output of ps is not a process!

 ```
 $ ps wc
  2424 tty2     Ssl+   0:00 gdm-x-session
 
   2426 tty2     Sl+   27:40 Xorg
   
   2442 tty2     Sl+    0:00 gnome-session-b
   
  46178 pts/0    Ss+    0:00 bash
  
  75634 pts/1    Ss+    0:00 bash
  
  76734 pts/1    T      0:00 bash
  
  76735 pts/1    T      0:00 wc
  
  76809 pts/1    T      0:00 bash
  
  76810 pts/1    T      0:00 sleep
  
  77803 pts/1    T      0:00 bash
  
  77804 pts/1    T      0:00 wc
  
  77817 pts/1    T      0:00 bash
  
  77818 pts/1    T      0:00 wc
  
  78521 pts/1    T      0:00 nano
  
  80264 pts/2    Ss+    0:00 bash
  
  80970 pts/2    T      0:00 cat
  
  82633 pts/2    T      0:00 nano
  
 182472 pts/3    Ss+    0:00 bash
 
 186316 pts/3    T      0:00 less
 
 186661 pts/3    T      0:00 less
 
 187451 pts/4    Ss     0:00 bash
 
 189339 pts/4    R+     0:00 ps```


