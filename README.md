# **30-Linux-System-Monitoring-Tools-Every-SysAdmin-Should-Know.**
Nilesh Salunke.

--------------------------------------------------------------------------------------------------------

# **1. top – Process activity monitoring command.**

The top command displays Linux processes. It provides a dynamic real-time view of a running system i.e. actual process activity. By default, it displays the most CPU-intensive tasks running on the server and updates the list every five seconds.
### # top
![Screen Shot 2020-12-29 at 11.40.32 AM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 11.40.32 AM.png)

Commonly Used Hot Keys With top Linux monitoring tools
Here is a list of useful hotkeys:
                                                                                                  
- t : Displays summary information off and on.                                                                                                 
- m : Displays memory information off and on.                                                                                                 
- A : Sorts the display by top consumers of various system resources. Useful for quick identification of performance-hungry tasks on a system. 

- f : Enters an interactive configuration screen for the top. Helpful for setting up top for a specific task.                                  

- o : Enables you to interactively select the ordering within the top.                                                                         
- r : Issues renice command.                                                                                                                  
- k : Issues kill command.                                                                                                                    
- z : Turn on or off-color/mono
 
--------------------------------------------------------------------------------------------------------

# **2. htop is similar to the top command but allows you to scroll vertically and horizontally and much more.**

htop is similar to the top command but allows you to scroll vertically and horizontally and much more.

### # htop
![Screen Shot 2020-12-29 at 12.42.36 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.42.36 PM.png)

--------------------------------------------------------------------------------------------------------

# **3. mpstat.**

If you are using SMP (Multiple CPU) systems, use the mpstat command to display the utilization of each CPU individually. It reports processors related statistics.

### # mpstat 
![Screen Shot 2020-12-29 at 12.43.44 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.43.44 PM.png)

--------------------------------------------------------------------------------------------------------

# **4. sar**
You can display today’s CPU activity, with the help of the sar command.

### # sar
![Screen Shot 2020-12-29 at 12.44.15 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.44.15 PM.png)

Comparison of CPU utilization
The sar command writes to standard output the contents of selected cumulative activity counters in the operating system. The accounting system, based on the values in the count and interval parameters. For example display comparison of CPU utilization; 2 seconds apart; 5 times, use:
### # sar -u 2 5
![Screen Shot 2020-12-29 at 12.46.07 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.46.07 PM.png)

Where, “-u 2 5”: The following values are displayed:

- %user: Percentage of CPU utilization that occurred while executing at the user level (application).
- %nice: Percentage of CPU utilization that occurred while executing at the user level with nice priority.
- %system: Percentage of CPU utilization that occurred while executing at the system level (kernel).
- %iowait: Percentage of time that the CPU or CPUs were idle during which the system had an outstanding disk I/O request.
- %idle: Percentage of time that the CPU or CPUs were idle and the system did not have an outstanding disk I/O request.

--------------------------------------------------------------------------------------------------------

# **5. vmstat – Virtual memory statistics**
The vmstat command reports information about processes, memory, paging, block IO, traps, and CPU activity.
### # vmstat 
![Screen Shot 2020-12-29 at 12.46.40 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.46.40 PM.png)

Field Description For Vm Mode

(a) procs are the process-related fields are:
- r: The number of processes waiting for run time.
- b: The number of processes in uninterruptible sleep.


(b) memory is the memory-related fields are:
- swpd: the amount of virtual memory used.
- free: the amount of idle memory.
- buff: the amount of memory used as buffers.
- cache: the amount of memory used as cache.


(c) swap is swap-related fields are:
- si: Amount of memory swapped in from disk (/s).
- so: Amount of memory swapped to disk (/s).


(d) io is the I/O-related fields are:
- bi: Blocks received from a block device (blocks/s).
- bo: Blocks sent to a block device (blocks/s).


(e) the system is the system-related fields are:
- in: The number of interrupts per second, including the clock.
- cs: The number of context switches per second.


(f) CPU is the CPU-related fields are:
These are percentages of total CPU time.
- us: Time spent running non-kernel code. (user time, including nice time)
- sy: Time spent running kernel code. (system time)
- id: Time spent idle. Prior to Linux 2.5.41, this includes IO-wait time.
- wa: Time spent waiting for IO. Prior to Linux 2.5.41, shown as zero.

--------------------------------------------------------------------------------------------------------

# **6. w – Find out who is logged on and what they are doing.**

### # w username
![Screen Shot 2020-12-29 at 12.47.19 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.47.19 PM.png)

--------------------------------------------------------------------------------------------------------

# **7. uptime.**
uptime command can be used to see how long the server has been running. The current time, how long the system has been running, how many users are currently logged on, and the system load averages for the past 1, 5, and 15 minutes.
### # uptime
![Screen Shot 2020-12-29 at 12.47.46 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.47.46 PM.png)

1 can be considered as the optimal load value. The load can change from system to system. For a single CPU system, 1 – 3 and SMP systems 6-10 load value might be acceptable.

--------------------------------------------------------------------------------------------------------

# **8. ps – Displays the Linux processes.**
ps command will report a snapshot of the current processes. To select all processes use the -A or -e option:

### # ps -A
![Screen Shot 2020-12-29 at 12.49.08 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.49.08 PM.png)

ps is just like the top command but provides more information.

### # ps -Al   - Show long format output.

### # ps -AlF  - To turn on extra full mode (it will show command-line arguments passed to process)

### # ps -AlFH - Display Threads.

### # ps -AlLm - Watch threads after the processes.

### # ps ax    - Print all processes on the server.
### # ps axu   - Print all processes on the server.

### # pstree  - Print a process tree.

### # ps -eo euser,ruser,suser,fuser,f,comm,label - Print security information of process.

### # ps axZ   - Print security information of process.

### # ps -eM   - Print security information of process.

### # ps -U nilesh -u nilesh u  - Prints all process running as user nilesh.

### # ps -auxf | sort -nr -k 4 | head -10  - top 10 memory consuming processes.

### # ps -auxf | sort -nr -k 3 | head -10  - top 10 CPU consuming process.

### # ps -aux | less  - All running process.

Where,
A : Select all processes
u : Select all processes on a terminal, including those of other users
x : Select processes without controlling ttys.

--------------------------------------------------------------------------------------------------------

# **9. free – Show Linux server memory usage.**
The free command shows the total amount of free and used physical and swap memory in the system, as well as the buffers used by the kernel.

### # free
![Screen Shot 2020-12-29 at 12.49.41 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.49.41 PM.png)

### # free -m or # #free -mt 

The free command can be used with the below options.

-b switch displays the amount of memory in bytes
-k switch (set by default) displays it in kilobytes
-m switch displays it in megabytes.
-t switch displays a line containing the totals.
-o switch disables the display of a “buffer adjusted” line. If the -o option is not specified, free subtracts buffer memory from the used memory and adds it to the free memory reported.
-s switch activates continuous polling delay seconds apart. You may actually specify any floating point number for delay, usleep(3) is used for microsecond resolution delay times.

--------------------------------------------------------------------------------------------------------

# 10. iostat – Montor Linux average CPU load and disk activity.
iostat command report Central Processing Unit (CPU) statistics and input/output statistics for devices, partitions, and network filesystems (NFS).
### # iostat
![Screen Shot 2020-12-29 at 12.50.09 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.50.09 PM.png)

--------------------------------------------------------------------------------------------------------

# **11. sar – Monitor, collect and report Linux system activity.**
sar command used to collect, report, and save system activity information.

### # sar -n DEV | more
![Screen Shot 2020-12-29 at 12.50.47 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 12.50.47 PM.png)

### # sar -n DEV -f /var/log/sa/sa24 | more  - The network counters from the 24th.
### # sar 4 5 - display real-time usage using sar.

--------------------------------------------------------------------------------------------------------

# **12. mpstat – Monitor multiprocessor usage on Linux.**

mpstat command displays activities for each available processor, processor 0 being the first one.

### # mpstat -P ALL
![]({{site.baseurl}}//Screen%20Shot%202020-12-29%20at%2012.51.22%20PM.png)

--------------------------------------------------------------------------------------------------------

# **13. netstat – Linux network and statistics monitoring tool.**
netstat command displays network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.

### # netstat -tulpn
### # netstat -nat
