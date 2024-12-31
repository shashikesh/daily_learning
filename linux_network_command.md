# Linux Networking Commands

A comprehensive list of essential Linux networking commands with descriptions and usage examples.

---

## 1. Basic Network Configuration

### - `ifconfig`
Used to configure or display network interfaces.

``` bash
ifconfig
ifconfig eth0 up   # `Used tp start Interface`
```
### - `ip`
Modern replacement for ifconfig.
``` bash
ip addr show
ip link set eth0 up
```
### - `ping`
Test network connectivity.
``` bash
ping google.com
ping -c 4 8.8.8.8
```

### - `traceroute`
Track the route packets take to a destination. It helps identify routing issues and network delays by showing each hop along the route to the target address

#### Common Options
- -n: Displays IP addresses instead of trying to resolve domain names.
- -w <seconds>: Specifies the timeout for each probe.
- -m <max_ttl>: Sets the maximum number of hops to probe.
- -q <queries>: Sets the number of probe packets per hop (default is 3).
- -I: Uses ICMP ECHO packets instead of UDP.
- -T: Uses TCP SYN packets.
``` bash
traceroute example.com
```

### - `mtr`
Combines `ping` and `traceroute`.
``` bash
mtr google.com
```

## DNS Management
### - `nslookup`
Query DNS for domain/IP information.

``` bash
nslookup google.com
```

### - `dig`
Perform DNS lookups.
``` bash
dig example.com
dig @8.8.8.8 example.com
```

## Network Traffic Monitoring
### - `netstat`
Display network connections, routing tables, and interface statistics.
#### Common Options
- `-a`:	Show all connections and listening ports.
- `-t`:	Show TCP connections.
- `-u`:	Show UDP connections.
- `-n`:	Display addresses and ports numerically (skip DNS resolution).
- `-p`:	Show the process ID (PID) and name of the program using each socket (requires root/administrator privileges).
- `-r`:	Display the system's routing table.
- `-i`:	Display a table of network interfaces.
- `-s`:	Display network statistics by protocol (e.g., TCP, UDP, ICMP).
- `--help`	Show
``` bash
netstat -a
netstat option
netstat -tuln  # Active Internet connection 
```
### - `ss`
Modern alternative to netstat
``` bash
ss -tuln
```
## File Transfers and Sharing
### - `scp`
Securely copy files between systems.
``` bash
scp file.txt user@remote:/path/to/destination
```
### - `rsync`
Efficient file synchronization and transfer.
``` bash
rsync -avz /local/dir user@remote:/remote/dir
```
#### Common Options
- `-a`:	Archive mode: Preserves permissions, symbolic links, timestamps, and directories.
- `-v`:	Verbose: Displays detailed progress.
- `-z`:	Compress file data during transfer.
- `-r`:	Recursive: Copy directories and their contents.
- `--progress`:	Show progress during the transfer.
- `-e`: ssh	Use SSH as the transport protocol for remote transfers.
- `--delete`:	Delete files in the destination that are no longer present in the source.
- `--exclude=<pattern>`:	Exclude files or directories matching a pattern.
- `-n` or `--dry-run`:	Show what would be done without actually performing the transfe
``` bash 
rsync -a /source/directory /destination/directory  #Basic Local Copy
rsync -avz -e ssh /local/path user@remote:/remote/path # Remote Synchronization Over SSH:
rsync -avn /source/ /destination/  #Remote Synchronization Over SSH:
```
### - `wget`
Download files from the web.
``` bash
wget http://example.com/file.tar.gz
```
### - `route`
Display or modify the routing table.
``` bash
route -n
route add default gw 192.168.1.1
```
## Advanced Tools
### - `iptables`
Configure firewall rules.
``` bash
iptables -L
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```
### - `nmap`
Network scanning and security auditing.
``` bash
nmap 192.168.1.0/24
nmap -sV example.com
```
### - `curl`
Transfer data using various protocols (HTTP, FTP, etc.).
``` bash
Copy code
curl http://example.com
curl -I http://example.com
```
## Network Diagnostics
### - `whois`
Query domain registration information.
``` bash
whois example.com
```
### telnet
Connect to a remote host for testing network services.
``` bash
telnet google.com 80
```
