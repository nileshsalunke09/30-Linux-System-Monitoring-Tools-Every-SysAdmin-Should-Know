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

# **2. htop - Process activity monitoring command.**

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

--------------------------------------------------------------------------------------------------------

# **14. pmap – Montor process memory usage on Linux.**
pmap command report memory map of a process. Use this command to find out causes of memory bottlenecks.

### # pmap -d PID

To display process memory information for pid # 632, enter:
### # pmap -d 632
![Screen Shot 2020-12-29 at 1.11.12 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.11.12 PM.png)

![Screen Shot 2020-12-29 at 1.13.00 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.13.00 PM.png)

The last line is very important:

- mapped: 152632K total amount of memory mapped to files
- writeable/private: 1280K the amount of private address space
- shared: 0K the amount of address space this process is sharing with others.

The -x option can be used to provide information about the memory allocation and mapping types per mapping. The amount of resident, non-shared anonymous, and locked memory is shown for each mapping:
![Screen Shot 2020-12-29 at 1.19.02 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.19.02 PM.png)
![Screen Shot 2020-12-29 at 1.19.42 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.19.42 PM.png)

--------------------------------------------------------------------------------------------------------

# **15. ss – Network Statistics.**
ss command use to dump socket statistics. It allows showing information similar to netstat. Please note that the netstat is mostly obsolete. Hence you need to use ss command. 

To ss all TCP and UDP sockets on Linux:

### # ss -t -a 

OR

### # ss -u -a
![Screen Shot 2020-12-29 at 1.17.03 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.17.03 PM.png)

Show all TCP sockets with process SELinux security contexts:

### # ss -t -a -Z

Show all newwork open ports:

### # ss -l
![Screen Shot 2020-12-29 at 1.21.42 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 1.21.42 PM.png)


- Find out who is responsible for opening socket / port # 4949 using the ss command and grep command:
### # ss -lp | grep port_number


- Display All TCP Sockets:
### # ss -t -a


- Display All UDP Sockets:
### # ss -u -a


- Display All RAW Sockets:
### # ss -w -a


- Display All UNIX Sockets:
### # ss -x -a


- Display All Established SMTP Connections:
### # ss -o state established '( dport = :smtp or sport = :smtp )'


- Display All Established HTTP Connections:
### # ss -o state established '( dport = :http or sport = :http )'


- Find All Local Processes Connected To X Server:
### # ss -x src /tmp/.X11-unix/*


- List All The Tcp Sockets in State FIN-WAIT-1:
### # ss -o state fin-wait-1 '( sport = :http or sport = :https )' dst 202.54.1/24



### ***How to filter sockets using TCP states?***


- For tcp ipv4
### # ss -4 state FILTER-NAME-HERE 


- For tcp ipv6
### # ss -6 state FILTER-NAME-HERE

Where FILTER-NAME-HERE can be any one of the following,

- established
- syn-sent
- syn-recv
- fin-wait-1
- fin-wait-2
- time-wait
- closed
- close-wait
- last-ack
- listen
- closing
- all : All of the above states
- connected : All the states except for listen and closed
- synchronized : All the connected states except for syn-sent
- bucket : Show states, which are maintained as minisockets, i.e. time-wait and syn-recv.
- big : Opposite to bucket state.

--------------------------------------------------------------------------------------------------------

# **16. iptraf – Get real-time network statistics on Linux**

iptraf command is interactive colorful IP LAN monitor. It is an ncurses-based IP LAN monitor that generates various network statistics including TCP info, UDP counts, ICMP and OSPF information, Ethernet load info, node stats, IP checksum errors, and others. It can provide the following info in easy to read format:
- Network traffic statistics by TCP connection
- IP traffic statistics by network interface
- Network traffic statistics by protocol
- Network traffic statistics by TCP/UDP port and by packet size
- Network traffic statistics by Layer2 address

[Install IPTraf on a Centos / RHEL / Fedora Linux To Get Network Statistics.](https://www.cyberciti.biz/faq/install-iptraf-centos-redhat-fedora-linux/)

--------------------------------------------------------------------------------------------------------

# **17. tcpdump – Detailed network traffic analysis**

tcpdump command is simple command that dump traffic on a network. However, you need good understanding of TCP/IP protocol to utilize this tool. For.e.g to display traffic info about DNS, enter:

### # tcpdump -i eth1 'udp port 53'


View all IPv4 HTTP packets to and from port 80, i.e. print only packets that contain data, not, for example, SYN and FIN packets and ACK-only packets, enter:

### # tcpdump 'tcp port 80 and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'


Show all FTP session to 202.54.1.5, enter:

### # tcpdump -i eth1 'dst 202.54.1.5 and (port 21 or 20)


Print all HTTP session to 192.168.1.5:

### # tcpdump -ni eth0 'dst 192.168.1.5 and tcp and port http'

--------------------------------------------------------------------------------------------------------

# **18. atop – Advanced Linux system & process monitor**

atop is a very powerful and an interactive monitor to view the load on a Linux system. It displays the most critical hardware resources from a performance point of view. You can quickly see CPU, memory, disk and network performance. It shows which processes are responsible for the indicated load concerning CPU and memory load on a process level.

### # atop
![Screen Shot 2020-12-29 at 2.34.16 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 2.34.16 PM.png)



- To see active processes only.
### # atop -a  -To see active processes only.


- Display individual threads.
### # atop -y


- Display network-related process-info.
### # atop -n


- Display scheduling-related process-info.
### # atop -s


- Display various process-info (ppid, user/group, date/time).
### # atop -v


- Display command line per process.
### # atop -c


- Pass the following option to sort your process:

      -C  sort processes in order of cpu-consumption (default)
	  -M  sort processes in order of memory-consumption
	  -D  sort processes in order of disk-activity
	  -N  sort processes in order of network-activity
	  -A  sort processes in order of most active resource (auto mode)

[CentOS / RHEL: Install atop (Advanced System & Process Monitor) Utility](https://www.cyberciti.biz/faq/centos-redhat-linux-install-atop-command-using-yum/)

--------------------------------------------------------------------------------------------------------

# **19. monit – Process supervision**

Monit is a free and open source software that acts as process supervision. It comes with the ability to restart services which have failed. You can use Systemd, daemontools or any other such tool for the same purpose. [This tutorial shows how to install and configure monit as Process supervision on Debian or Ubuntu Linux](https://www.cyberciti.biz/faq/how-to-install-and-use-monit-on-ubuntudebian-linux-server/).

--------------------------------------------------------------------------------------------------------

# **20. nethogs- Find out PIDs that using most bandwidth on Linux**

NetHogs is a small but handy net top tool. It groups bandwidth by process name such as Firefox, wget and so on. If there is a sudden burst of network traffic, start NetHogs. You will see which PID is causing bandwidth surge.

### # nethogs
![Screen Shot 2020-12-29 at 2.44.36 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 2.44.36 PM.png)

[Install nethogs using this link.](https://www.cyberciti.biz/faq/linux-find-out-what-process-is-using-bandwidth/)

--------------------------------------------------------------------------------------------------------

# **21. iftop – Show bandwidth usage on an interface by host**

iftop command listens to network traffic on a given interface name such as eth0. It displays a table of current bandwidth usage by pairs of hosts.

### # iftop
![Screen Shot 2020-12-29 at 2.47.41 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 2.47.41 PM.png)


[Install iftop using this link.](https://www.cyberciti.biz/faq/linux-find-out-what-process-is-using-bandwidth/)

--------------------------------------------------------------------------------------------------------

# **23. nmon – Linux systems administrator, tuner, benchmark tool**

nmon is a Linux sysadmin’s ultimate tool for the tunning purpose. It can show CPU, memory, network, disks, file systems, NFS, top process resources and partition information from the cli.

### # nmon
![Screen Shot 2020-12-29 at 2.55.53 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 2.55.53 PM.png)

--------------------------------------------------------------------------------------------------------

# **24. glances – Keep an eye on Linux system**

glances is an open source cross-platform monitoring tool. It provides tons of information on the small screen. It can also work in client/server mode.

### # glances
![]({{site.baseurl}}//Screen%20Shot%202020-12-29%20at%202.57.29%20PM.png)![Screen Shot 2020-12-29 at 2.57.29 PM.png]({{site.baseurl}}/Screen Shot 2020-12-29 at 2.57.29 PM.png)


### # glances (option)

Use the following hot keys to find tune your output:

- a Sort processes automatically.
- c Sort processes by CPU%.
- m Sort processes by MEM%.
- p Sort processes by name.
- i Sort processes by I/O rate.
- d Show/hide disk I/O stats.
- f Show/hide file system stats.
- n Show/hide network stats.
- s Show/hide sensors stats.
- y Show/hide hddtemp stats.
- l Show/hide logs.
- b Bytes or bits for network I/O.
- w Delete warning logs.
- x Delete warning and critical logs.
- 1 Global CPU or per-CPU stats.
- t View network I/O as combination.
- u – View cumulative network I/O.


Refresh information every 5 seconds:
### # # glances -t 5


To see all supported options:
### # glances -h

--------------------------------------------------------------------------------------------------------

# **25. strace – Monitor system calls on Linux**

strace is a useful diagnostic, instructional, and debugging tool. It can save lots of headache. System administrators, diagnosticians and trouble-shooters will find it invaluable for solving problems with programs for which the source is not readily available since they do not need to be recompiled in order to trace them. This is also useful to submit bug reports to open source developers.

Run strace against /bin/foo and capture its output to a text file in output.txt:
### # strace -o output.txt /bin/foo


You can strace the webserver process and see what it’s doing. For example, strace php5 fastcgi process, enter:
### # strace -p 22254 -s 80 -o /tmp/debug.lighttpd.txt


To see only a trace of the open, read system calls, enter :
### # strace -e trace=open,read -p 22254 -s 80 -o debug.webserver.txt


Where,

-o filename : Write the trace output to the file filename rather than to screen (stderr).

-p PID : Attach to the process with the process ID pid and begin tracing. The trace may be terminated at any time by a keyboard interrupt signal (hit CTRL-C). strace will respond by detaching itself from the traced process(es) leaving it (them) to continue running. Multiple -p options can be used to attach to up to 32 processes in addition to command (which is optional if at least one -p option is given).

-s SIZE : Specify the maximum string size to print (the default is 32).


Refer to strace man page for more information:
### # man strace

--------------------------------------------------------------------------------------------------------

# **26. /proc/ file system – Various Linux kernel statistics**

/proc file system provides detailed information about various hardware devices and other Linux kernel information.

### # cat /proc/cpuinfo
### # cat /proc/meminfo
### # cat /proc/zoneinfo
### # cat /proc/mounts

--------------------------------------------------------------------------------------------------------
