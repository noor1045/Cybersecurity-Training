# Week 2 Day 6: Nmap Automation Script

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I created a Python script to automate basic Nmap scans. The script takes input from the command line and runs the selected Nmap scan on an authorized target.

For testing, I used the localhost address `127.0.0.1`, which represents my own Kali Linux system.

## Python Script

The script is saved as:

```text
nmap_auto.py
```

The following Python modules are used in the script:

```python
import argparse
import ipaddress
import json
import re
import shutil
import subprocess
from datetime import datetime
```

The script uses `argparse` for command-line options and `subprocess` to run Nmap commands.

It also checks the target and port values before starting a scan.

## Features Added

The script includes the following options:

- Port scanning
- Service and version detection
- Operating system detection
- Ping sweep
- Custom port selection
- Nmap timing options from T0 to T5
- Target validation
- Port validation
- JSON result export
- Author information and authorized-use notice

## Help Menu Test

I tested the help menu using:

```bash
python3 nmap_auto.py --help
```

The command displayed the available options, including:

```text
-t, --target
--port-scan
--service-scan
--os-scan
--ping-sweep
--ports
--timing
--output
```

## Port Scan

The first scan performed was a port scan on localhost.

Command used:

```bash
python3 nmap_auto.py -t 127.0.0.1 --port-scan --ports 1-1000
```

The script created and ran this Nmap command:

```text
nmap -T3 -p 1-1000 127.0.0.1
```

The scan checked ports 1 to 1000 on the local Kali Linux system.

## Service and Version Scan

The second test was a service and version scan.

Command used:

```bash
python3 nmap_auto.py -t 127.0.0.1 --service-scan --ports 1-1000
```

The script ran:

```text
nmap -T3 -sV -p 1-1000 127.0.0.1
```

The result showed that the localhost was active, but no open ports were found in the selected range.

The main result was:

```text
Host is up.
Not shown: 1000 closed TCP ports.
```

The scan completed successfully.

## Safety Note

All scans were performed on:

```text
127.0.0.1
```

This is the localhost address of my own Kali Linux machine. The script should only be used on systems that are owned by the user or where permission has been given.

## Remaining Work

The following steps are still left:

- Generate JSON output
- Test invalid port input
- Take screenshots of both results
- Upload the Python file and output file
- Complete the final README

## Status

In Progress
