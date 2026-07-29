# Week 2 Day 10: Combining Tools for Comprehensive Assessment

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I created a Bash script that combines different security assessment tools into one automated workflow.

Instead of running every tool separately, the script takes a target IP address and automatically performs network reconnaissance, web application scanning, vulnerability scanning and basic report generation.

The practical was performed against my own authorized localhost system using the target address:

`127.0.0.1`

## Objective

The main purpose of this task was to:

- Automate initial reconnaissance and vulnerability scanning
- Identify open ports and running services
- Detect web applications on common web ports
- Run web vulnerability assessment tools
- Save all scan results in a separate folder
- Generate a basic security assessment report

## Tools Used

The following tools were combined in the script:

- Nmap for port, service and vulnerability scanning
- Nikto for web server vulnerability scanning
- Dirb for web directory discovery
- WPScan for WordPress assessment
- Bash for automating the complete workflow

## Bash Script

The script was saved with the following name:

`comprehensive_assessment.sh`

The script accepts the target IP as a command-line argument and creates a new timestamped folder for the assessment results.

Example:

`./comprehensive_assessment.sh 127.0.0.1`

## Script Permission

The script was made executable using:

`chmod +x comprehensive_assessment.sh`

After this, it was ready to run directly from the terminal.

## Network Reconnaissance

The first stage of the script used Nmap to detect open ports, services, versions and operating-system information.

The Nmap scan results were saved in three formats:

- `nmap_scan.nmap`
- `nmap_scan.gnmap`
- `nmap_scan.xml`

The script also extracted the open ports from the Nmap output so they could be used in the next stages.

## Web Application Scanning

When a web service was detected, the script automatically ran the following tools:

- Nikto
- Dirb
- WPScan

Nikto checked the web server for common security issues and missing security headers.

Dirb searched for accessible files and directories on the web server.

WPScan was included to perform additional checks if the detected website was running WordPress.

The results were saved as:

- `nikto_scan.txt`
- `dirb_scan.txt`
- `wpscan.txt`

## Vulnerability Assessment

After the initial scans, the script used Nmap vulnerability scripts against the detected open ports.

The vulnerability scan results were saved as:

- `nmap_vuln_scan.nmap`
- `nmap_vuln_scan.gnmap`
- `nmap_vuln_scan.xml`

## Preliminary Report

At the end of the assessment, the script automatically generated a Markdown report named:

`preliminary_report.md`

The report included:

- Target IP address
- Assessment date
- Detected network services
- Possible vulnerabilities
- Basic security recommendations

## Generated Output

All results were saved inside a timestamped assessment folder.

The final folder contained the Nmap results, web scanning results, vulnerability scan results and the preliminary report.

## What I Learned

From this task, I learned how multiple cybersecurity tools can be combined in one Bash script.

I also learned how automation can save time, keep scan results organized and create a consistent workflow for initial security assessments.

Automated scan results should still be reviewed manually because tools may report false positives or miss issues that require deeper testing.

## Safety Note

This practical was performed only on an authorized local system.

Security scanning should only be performed on systems that are personally owned or where written permission has been provided.

## Status

Completed
