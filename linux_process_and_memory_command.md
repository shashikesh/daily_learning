# Linux Process and Memory Management Commands

This document provides a detailed guide to commands for monitoring, managing processes, and memory usage in Linux.

---

## Process Management

- `ps`  
  Display information about active processes.  
  Examples:  
  ```bash
  ps                 # List processes for the current shell
  ps aux             # Show all processes with detailed information
  ps -ef             # Display full-format listing of processes
- `top`  
Display real-time information about system processes.
Example:  
``` bash
top
```
- `htop`  
Interactive process viewer (alternative to top).  
Example:
``` bash
htop
```
- `jobs`  
List active jobs in the current shell.  
Example:
``` bash
jobs
```
- `kill`  
Terminate a process by its PID.  
Examples:
```bash
kill 1234           # Terminate process with PID 1234
kill -9 1234        # Forcefully terminate the process
```
- `pkill`  
Terminate processes by name.  
Example:
``` bash
pkill process_name
```
- `killall`  
Terminate all processes with a given name.  
Example:
``` bash
killall process_name
```
- `bg`  
Resume a job in the background.  
Example:
```bash
bg %1
```
- `fg`  
Resume a job in the foreground.  
Example:
``` bash
fg %1
```
- `nice`  
Start a process with a specified priority.  
Example:
``` bash
nice -n 10 command
```
- `renice`  
Change the priority of an already running process.  
Example:
``` bash
renice -n 5 -p 1234
```
## Process Monitoring
- `pidof`  
Find the PID of a process by name.  
Example:
``` bash
pidof process_name
```
- `pgrep`  
Search for processes by name.  
Example:
```bash
pgrep process_name
```
- `strace`  
Trace system calls and signals.  
Example:
```bash
strace -p 1234
```
- `lsof`  
List open files by processes.
Examples:
```bash
lsof
lsof -p 1234         # Show files opened by process 1234
```
## Memory Management
- `free`  
Display memory usage.
Examples:
```bash
free
free -h              # Show in human-readable format
```
- `vmstat`  
Report system performance statistics.  
Example:
```bash
vmstat
```
- `top`  
Monitor memory usage in real time.  
Example:
``` bash
Copy code
top
```
- `htop`  
Interactive memory usage monitoring.  
Example:

``` bash
Copy code
htop
```
- `watch`  
Periodically run a command to monitor changes.  
Example:
```bash
Copy code
watch free -h
```
- `cat /proc/meminfo`  
View detailed memory usage information.
Example:
``` bash
Copy code
cat /proc/meminfo
```
- `cat /proc/swaps`  
Display information about swap usage.  
Example:
```bash
Copy code
cat /proc/swaps
```
- ```swapoff``` and ```swapon```  
Enable or disable swap space.  
Examples:
```bash
Copy code
swapoff /swapfile
swapon /swapfile
```
- `sysctl`  
Modify or view kernel parameters, including memory settings.  
Examples:

```bash
Copy code
sysctl -a | grep vm
sysctl -w vm.swappiness=10
```
### Advanced Process and Memory Commands
- `nice` and `renice`  
Control process priorities.  
Examples:
```bash
Copy code
nice -n 10 command
renice -n 5 -p 1234
```
- `ulimit`  
Display or set limits on system resources.  
Example:  

``` bash
Copy code
ulimit -n 1024       # Set maximum number of open files
```
- `cgroups`  
Manage and limit system resources for groups of processes.  
Example:
```bash
Copy code
cgcreate -g memory:/group_name
cgset -r memory.limit_in_bytes=512M group_name
```
- `ionice`  
Set I/O scheduling class and priority for a process.  
Example:
```bash
Copy code
ionice -c2 -n7 -p 1234
```
- `sar`  
Collect and report system activity, including memory and CPU usage.
Example:
``` bash
Copy code
sar -r
```
