# Cybersecurity Training — Week 1, Day 5

## Task Title

Nmap Automation Script — Python CLI Wrapper

## Task Objective

The objective of this task is to create a Python command-line script that automates common Nmap network-scanning operations.

Instead of manually writing complete Nmap commands, the user will be able to provide simple command-line options for tasks such as port scanning, service detection, operating-system detection, host discovery, timing selection, and result export.

The final script will use Python to safely call the installed Nmap program and display the results in a clean and readable format.

## Purpose of the Task

The main purpose of this task is to understand how Python can be used for network and system automation.

Through this task, I will learn how to:

Build a command-line application using Python
Use `argparse` to accept user options
Execute Nmap through Python
Validate user-provided targets and port ranges
Handle errors properly
Export scan results to a file
Add author and registration information to the script
Demonstrate the tool using an authorized target

This script will only be used against systems owned by me or systems for which explicit permission has been provided.

## Assignment Requirements

The assignment requires a single Python file that acts as a wrapper around Nmap.

The script should include at least five of the following features:

Host and port scanning
Custom port-range support
Service and version detection
Operating-system detection
Ping sweep or host discovery
Scan timing profiles from T0 to T5
Scan-result export in TXT, CSV, or JSON format
Optional Nmap script scanning


## Work Completed

I started this task by creating the Python file:

text
nmap_auto.py

I added a watermark and author-information section at the top of the script.

The watermark currently includes:

Task title
Author name
Registration number
Date
Course or training information
Authorized-use notice

The following information was included:

text
Name: Noor E Eman
Registration Number: BCS233016
Task: Nmap Automation Script
Course: Cybersecurity Training


I also created a simple startup banner that displays the same author and task information when the script is executed.

The basic script was tested using:

bash
python3 nmap_auto.py

The script successfully displayed the watermark banner and the message:

text
The Nmap automation tool is ready.

## Issue Faced

After completing the watermark and basic banner, I became confused about the next stage of the script.

At that point, the script only contained the basic structure and did not yet include the complete Nmap automation functionality.

The following parts were not completed during the previous session:

Argument parsing
Target validation
Port-range validation
Nmap command construction
Port scanning
Service detection
Operating-system detection
Ping sweep
Timing-profile selection
Output export
Error handling
Final testing

The task was therefore paused after the watermark and startup-banner stage.

## Current Script Stage

The current Python file contains:

Author watermark
Registration number
Authorized-use notice
Basic imports
Startup-banner function
Basic `main()` function
Correct Python entry-point structure

The current entry point is:

python
if __name__ == "__main__":
    show_banner()
    main()


The script can currently run without a syntax error, but the actual Nmap scanning features still need to be implemented.

## Work Planned for Today

Today, I will continue the task and complete the remaining functionality.

The next steps are:

1. Verify that Python and Nmap are installed.
2. Add a complete `argparse` command-line interface.
3. Add target validation for IP addresses, hostnames, and CIDR ranges.
4. Add validation for ports and port ranges.
5. Add a port-scan option.
6. Add service and version detection.
7. Add operating-system detection.
8. Add ping sweep or host discovery.
9. Add timing-profile support from T0 to T5.
10. Add TXT, CSV, or JSON output export.
11. Add clear error handling.
12. Test the script against an authorized local target.
13. Capture screenshots of at least two implemented features.
14. Upload the completed Python file and sample output to GitHub.

## Planned Command-Line Options

The final script is expected to support commands similar to:

bash
python3 nmap_auto.py --help


bash
python3 nmap_auto.py -t 127.0.0.1 --port-scan --ports 1-1000


```bash
python3 nmap_auto.py -t 127.0.0.1 --service-scan --ports 1-1000
```

bash
sudo python3 nmap_auto.py -t 127.0.0.1 --os-scan


bash
python3 nmap_auto.py -t AUTHORIZED_SUBNET --ping-sweep


bash
python3 nmap_auto.py -t 127.0.0.1 --service-scan \
ports 1-1000 --output json --outfile sample-output.json


## Safety and Authorization

Nmap can be used to identify systems, ports, services, and operating-system information.

For this reason, the script will only be tested on:

127.0.0.1`
My own Kali Linux virtual machine
My own systems
Networks for which I have explicit authorization

The script will not be used to scan random public IP addresses, third-party systems, or unauthorized networks.

The assignment also specifically warns that unauthorized scanning may be illegal. :contentReference[oaicite:1]{index=1

## Tools Used

Kali Linux
Python 3
Nmap
Nano Text Editor
Python `argparse`
Python `subprocess`
GitHub

## Progress Summary

The watermark, author information, authorized-use notice, and basic startup banner have been completed successfully.

The full command-line functionality and Nmap automation features are still in progress and will be completed during the current session.

## Task Status

In Progress
