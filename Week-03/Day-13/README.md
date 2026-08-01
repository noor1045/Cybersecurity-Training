# Week 3 Day 13: Dirsearch Directory Bruteforcing Tool

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I installed and used Dirsearch in Kali Linux.

Dirsearch is a Python-based command-line tool used to search for hidden files and directories on web servers. It can help identify resources such as admin panels, configuration files and unlisted folders.

## Repository Setup

I downloaded the Dirsearch repository using:

`git clone https://github.com/maurosoria/dirsearch.git`

After cloning the repository, I opened the folder using:

`cd dirsearch`

I then made the Python script executable using:

`chmod +x dirsearch.py`

## First Scan Attempt

I first tried to run Dirsearch against the target provided in the manual:

`python3 dirsearch.py -u http://testphp.vulnweb.com`

The scan could not start because a required Python module named `defusedcsv` was missing.

## Dependency Installation Issue

I tried to install the required dependencies using:

`pip3 install -r requirements.txt`

Kali Linux returned an `externally-managed-environment` error. This meant that the packages could not be installed directly in the system Python environment.

## Virtual Environment Setup

To solve the dependency issue, I installed Python virtual environment support using:

`sudo apt install python3-venv -y`

I created a virtual environment using:

`python3 -m venv venv`

The virtual environment was activated using:

`source venv/bin/activate`

After activation, `(venv)` appeared at the start of the terminal prompt.

## Installing Dependencies

Inside the virtual environment, I installed the required packages using:

`pip install -r requirements.txt`

The dependencies were installed successfully, and Dirsearch was ready to run.

## Target Connection Issue

I tried the original target again:

`python3 dirsearch.py -u http://testphp.vulnweb.com`

The scan ended with a request timeout because the target server was not responding.

I checked the target using ping, nslookup and curl.

The domain resolved successfully to an IP address, but both HTTP and HTTPS connections failed. This confirmed that the issue was with the target server and not with the Dirsearch installation.

## Alternative Target Scan

Following the supervisor's instruction, I used the alternative test target:

`python3 dirsearch.py -u https://httpbin.org`

Dirsearch started successfully and completed the scan.

The scan did not find any matching hidden directories or files on the alternative target, but the tool completed without dependency or connection errors.

## Result

Dirsearch was installed and configured successfully inside a Python virtual environment.

The original target was unavailable, so the practical was completed using the supervisor-provided alternative target.

The final scan ended with the message:

`Task Completed`

## What I Learned

In this task, I learned how to clone and run a Python security tool from GitHub.

I also learned how to handle missing dependencies, create and activate a Python virtual environment, install packages safely and troubleshoot target connection problems.

## Safety Note

Dirsearch should only be used against systems that are personally owned or where proper authorization has been provided.

## Status

Completed
