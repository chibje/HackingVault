# Nmap Cheatsheet

Usage:

```bash
nmap [ <Scan Type> ...] [ <Options> ] { <target specification> }
```

## Basic Scanning Techniques

The `-s` switch determines the type of scan to perform.

|Nmap Switch|Description|
|:--|:--|
|**-sA**|ACK scan|
|**-sF**|FIN scan|
|**-sI**|IDLE scan|
|**-sL**|DNS scan (a.k.a. list scan)|
|**-sN**|NULL scan|
|**-sO**|Protocol scan|
|**-sP**|Ping scan|
|**-sR**|RPC scan|
|**-sS**|SYN scan|
|**-sT**|TCP connect scan|
|**-sW**|Windows scan|
|**-sX**|XMAS scan|
### Scan a Single Target


```shell
nmap [target]
```

### Scan Multiple Targets

```shell
nmap [target1, target2, etc]
```

### Scan a List of Targets

```shell
nmap -iL [list.txt]
```

### Scan a Range of Hosts
```shell
nmap [range of IP addresses]
```

### Scan an Entire Subnet
```shell
nmap [ip address/cdir]
```

### Scan Random Hosts
```shell
nmap -iR [number]
```

### Exclude Targets From a Scan

```shell
nmap [targets] --exclude [targets]
```

### Exclude Targets Using a List

```shell
nmap [targets] --excludefile [list.txt]
```

### Perform an Aggresive Scan

```shell
nmap -A [target]
```

### Scan an IPv6 Target


```shell
nmap -6 [target]
```

## Port Scanning Options


### Perform a Fast Scan


```shell
nmap -F [target]
```

### Scan Specific Ports



```shell
nmap -p [port(s)] [target]
```

### Scan Ports by Name



```shell
nmap -p [port name(s)] [target]
```

### Scan Ports by Protocol

```shell
nmap -sU -sT -p U:[ports],T:[ports] [target]
```

### Scan All Ports

```shell
nmap -p 1-65535 [target]
```

### Scan Top Ports

```shell
nmap --top-ports [number] [target]
```

### Perform a Sequential Port Scan


```shell
nmap -r [target]
```

### Attempt to Guess an Unknown OS

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#attempt-to-guess-an-unknown-os)

```shell
nmap -O --osscan-guess [target]
```

### Service Version Detection

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#service-version-detection)

```shell
nmap -sV [target]
```

### Troubleshoot Version Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#troubleshoot-version-scan)

```shell
nmap -sV --version-trace [target]
```

### Perform a RPC Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#perform-a-rpc-scan)

```shell
nmap -sR [target]
```

## Discovery Options

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#discovery-options)

**Host Discovery** The `-p` switch determines the type of ping to perform.

|Nmap Switch|Description|
|:--|:--|
|**-PI**|ICMP ping|
|**-Po**|No ping|
|**-PS**|SYN ping|
|**-PT**|TCP ping|

### Perform a Ping Only Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#perform-a-ping-only-scan)

```shell
nmap -sn [target]
```

### Do Not Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#do-not-ping)

```shell
nmap -Pn [target]
```

### TCP SYN Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-syn-ping)

```shell
nmap -PS [target]
```

### TCP ACK Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-ack-ping)

```shell
nmap -PA [target]
```

### UDP Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#udp-ping)

```shell
nmap -PU [target]
```

### SCTP INIT Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#sctp-init-ping)

```shell
nmap -PY [target]
```

### ICMP Echo Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#icmp-echo-ping)

```shell
nmap -PE [target]
```

### ICMP Timestamp Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#icmp-timestamp-ping)

```shell
nmap -PP [target]
```

### ICMP Address Mask Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#icmp-address-mask-ping)

```shell
nmap -PM [target]
```

### IP Protocol Ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#ip-protocol-ping)

```shell
nmap -PO [target]
```

### ARP ping

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#arp-ping)

```shell
nmap -PR [target]
```

### Traceroute

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#traceroute)

```shell
nmap --traceroute [target]
```

### Force Reverse DNS Resolution

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#force-reverse-dns-resolution)

```shell
nmap -R [target]
```

### Disable Reverse DNS Resolution

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#disable-reverse-dns-resolution)

```shell
nmap -n [target]
```

### Alternative DNS Lookup

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#alternative-dns-lookup)

```shell
nmap --system-dns [target]
```

### Manually Specify DNS Server

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#manually-specify-dns-server)

Can specify a single server or multiple.

```shell
nmap --dns-servers [servers] [target]
```

### Create a Host List

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#create-a-host-list)

```shell
nmap -sL [targets]
```

## Port Specification and Scan Order

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#port-specification-and-scan-order)

|Nmap Switch|Description|
|:--|:--|

## Service/Version Detection

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#serviceversion-detection)

|Nmap Switch|Description|
|:--|:--|
|**-sV**|Enumerates software versions|

## Script Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#script-scan)

|Nmap Switch|Description|
|:--|:--|
|**-sC**|Run all default scripts|

## OS Detection

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#os-detection)

|Nmap Switch|Description|
|:--|:--|

## Timing and Performance

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#timing-and-performance)

The `-t` switch determines the speed and stealth performed.

|Nmap Switch|Description|
|:--|:--|
|**-T0**|Serial, slowest scan|
|**-T1**|Serial, slow scan|
|**-T2**|Serial, normal speed scan|
|**-T3**|Parallel, normal speed scan|
|**-T4**|Parallel, fast scan|

Not specifying a `T` value will default to `-T3`, or normal speed.

## Firewall Evasion Techniques

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#firewall-evasion-techniques)

### Firewall/IDS Evasion and Spoofing

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#firewallids-evasion-and-spoofing)

|Nmap Switch|Description|
|:--|:--|

### Fragment Packets

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#fragment-packets)

```shell
nmap -f [target]
```

### Specify a Specific MTU

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#specify-a-specific-mtu)

```shell
nmap --mtu [MTU] [target]
```

### Use a Decoy

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#use-a-decoy)

```shell
nmap -D RND:[number] [target]
```

### Idle Zombie Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#idle-zombie-scan)

```shell
nmap -sI [zombie] [target]
```

### Manually Specify a Source Port

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#manually-specify-a-source-port)

```shell
nmap --source-port [port] [target]
```

### Append Random Data

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#append-random-data)

```shell
nmap --data-length [size] [target]
```

### Randomize Target Scan Order

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#randomize-target-scan-order)

```shell
nmap --randomize-hosts [target]
```

### Spoof MAC Address

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#spoof-mac-address)

```shell
nmap --spoof-mac [MAC|0|vendor] [target]
```

### Send Bad Checksums

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#send-bad-checksums)

```shell
nmap --badsum [target]
```

## Advanced Scanning Functions

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#advanced-scanning-functions)

### TCP SYN Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-syn-scan)

```shell
nmap -sS [target]
```

### TCP Connect Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-connect-scan)

```
nmap -sT [target]
```

### UDP Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#udp-scan)

```shell
nmap -sU [target]
```

### TCP NULL Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-null-scan)

```shell
nmap -sN [target]
```

### TCP FIN Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-fin-scan)

```shell
nmap -sF [target]
```

### Xmas Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#xmas-scan)

```shell
nmap -sA [target]
```

### TCP ACK Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#tcp-ack-scan)

```shell
nmap -sA [target]
```

### Custom TCP Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#custom-tcp-scan)

```shell
nmap --scanflags [flags] [target]
```

### IP Protocol Scan

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#ip-protocol-scan)

```shell
nmap -sO [target]
```

### Send Raw Ethernet Packets

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#send-raw-ethernet-packets)

```shell
nmap --send-eth [target]
```

### Send IP Packets

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#send-ip-packets)

```shell
nmap --send-ip [target]
```

## Timing Options

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#timing-options)

### Timing Templates

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#timing-templates)

```shell
nmap -T[0-5] [target]
```

### Set the Packet TTL

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#set-the-packet-ttl)

```shell
nmap --ttl [time] [target]
```

### Minimum NUmber of Parallel Operations

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#minimum-number-of-parallel-operations)

```shell
nmap --min-parallelism [number] [target]
```

### Maximum Number of Parallel Operations

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maximum-number-of-parallel-operations)

```shell
nmap --max-parallelism [number] [target]
```

### Minimum Host Group Size

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#minimum-host-group-size)

```shell
nmap --min-hostgroup [number] [targets]
```

### Maximum Host Group Size

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maximum-host-group-size)

```shell
nmap --max-hostgroup [number] [targets]
```

### Maximum RTT Timeout

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maximum-rtt-timeout)

```shell
nmap --initial-rtt-timeout [time] [target]
```

### Initial RTT Timeout

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#initial-rtt-timeout)

```shell
nmap --max-rtt-timeout [TTL] [target]
```

### Maximum Number of Retries

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maximum-number-of-retries)

```shell
nmap --max-retries [number] [target]
```

### Host Timeout

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#host-timeout)

```shell
nmap --host-timeout [time] [target]
```

### Minimum Scan Delay

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#minimum-scan-delay)

```shell
nmap --scan-delay [time] [target]
```

### Maxmimum Scan Delay

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maxmimum-scan-delay)

```shell
nmap --max-scan-delay [time] [target]
```

### Minimum Packet Rate

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#minimum-packet-rate)

```shell
nmap --min-rate [number] [target]
```

### Maximum Packet Rate

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#maximum-packet-rate)

```shell
nmap --max-rate [number] [target]
```

### Defeat Reset Rate Limits

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#defeat-reset-rate-limits)

```shell
nmap --defeat-rst-ratelimit [target]
```

## Output Options

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#output-options)

|Nmap Switch|Description|
|:--|:--|
|`-oN`|Normal output|
|`-oX`|XML output|
|`-oA`|Normal, XML, and Grepable format all at once|

### Save Output to a Text File

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#save-output-to-a-text-file)

```shell
nmap -oN [scan.txt] [target]
```

### Save Output to a XML File

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#save-output-to-a-xml-file)

```shell
nmap -oX [scan.xml] [target]
```

### Grepable Output

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#grepable-output)

```shell
nmap -oG [scan.txt] [target]
```

### Output All Supported File Types

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#output-all-supported-file-types)

```shell
nmap -oA [path/filename] [target]
```

### Periodically Display Statistics

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#periodically-display-statistics)

```shell
nmap --stats-every [time] [target]
```

### 1337 Output

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#1337-output)

```shell
nmap -oS [scan.txt] [target]
```

## Compare Scans

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#compare-scans)

### Comparison Using Ndiff

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#comparison-using-ndiff)

```shell
ndiff [scan1.xml] [scan2.xml]
```

### Ndiff Verbose Mode

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#ndiff-verbose-mode)

```shell
ndiff -v [scan1.xml] [scan2.xml]
```

### XML Output Mode

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#xml-output-mode)

```shell
ndiff --xml [scan1.xml] [scan2.xml]
```

## Troubleshooting and Debugging

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#troubleshooting-and-debugging)

### Get Help

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#get-help)

```shell
nmap -h
```

### Display Nmap Version

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#display-nmap-version)

```shell
nmap -V
```

### Verbose Output

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#verbose-output)

```shell
nmap -v [target]
```

### Debugging

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#debugging)

```shell
nmap -d [target]
```

### Display Port State Reason

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#display-port-state-reason)

```shell
nmap --reason [target]
```

### Only Display Open Ports

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#only-display-open-ports)

```shell
nmap --open [target]
```

### Trace Packets

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#trace-packets)

```shell
nmap --packet-trace [target]
```

### Display Host Networking

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#display-host-networking)

```shell
nmap --iflist
```

### Specify a Network Interface

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#specify-a-network-interface)

```shell
nmap -e [interface] [target]
```

## Nmap Scripting Engine

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#nmap-scripting-engine)

### Execute Individual Scripts

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#execute-individual-scripts)

```shell
nmap --script [script.nse] [target]
```

### Execute Multiple Scripts

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#execute-multiple-scripts)

```shell
nmap --script [expression] [target]
```

### Execute Scripts by Category

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#execute-scripts-by-category)

```shell
nmap --script [category] [target]
```

### Execute Multiple Script Categories

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#execute-multiple-script-categories)

```shell
nmap --script [category1,category2,etc]
```

### Troubleshoot Scripts

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#troubleshoot-scripts)

```shell
nmap --script [script] --script-trace [target]
```

### Update the Script Database

[](https://github.com/jasonniebauer/Nmap-Cheatsheet#update-the-script-database)

```shell
nmap --script-updatedb
```