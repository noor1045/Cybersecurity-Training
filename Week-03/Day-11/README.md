# Week 3 Day 11: Custom Security Assessment Tool

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I created a Python-based custom security assessment tool in Kali Linux.

The tool automatically runs an Nmap scan, checks the SSL/TLS configuration using sslscan, and saves the results in a JSON report.

## Requirements

Before creating the tool, I verified the installation of:

- Python 3
- Nmap
- sslscan

## Folder and Python File

I created a folder named:

`custom_tool`

Inside this folder, I created the Python file:

`custom_assessor.py`

## Tool Functions

The Python tool performs the following tasks:

- Accepts a target IP address or hostname
- Runs an Nmap service and script scan
- Checks SSL/TLS configuration using sslscan
- Stores the scan results
- Generates a JSON assessment report

## Script Permission

The Python script was made executable using:

`chmod +x custom_assessor.py`

## Running the Tool

The tool was run using:

`./custom_assessor.py 162.159.135.42`

After running, the tool displayed the Nmap scan, SSL/TLS check, and report generation messages.

## Generated Report

The tool created the following JSON report:

`assessment_162_159_135_42.json`

The report contained:

- Target IP address
- Scan timestamp
- Nmap output
- sslscan output
- Assessment findings

The JSON file was opened and checked successfully.

## Issue Faced

While creating the Python script, I faced indentation errors because some lines had different spacing.

I corrected the indentation and checked the script using:

`python3 -m py_compile custom_assessor.py`

After fixing the spacing, the script ran successfully.

## What I Learned

From this task, I learned how Python can be used to automate basic security assessment tasks.

I also learned how to run external security tools through Python, generate JSON reports, manage script permissions, and fix indentation errors.

## Safety Note

The tool should only be used on systems that are owned by the user or where proper authorization has been provided.

## Status

Completed
