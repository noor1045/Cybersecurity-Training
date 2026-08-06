# Week 04 – Day 17: GoSpider

## Overview

In this practical task, I installed and tested GoSpider, a fast web crawling tool written in Golang. GoSpider is used during web application reconnaissance to discover URLs, JavaScript files, subdomains, links, and hidden endpoints.

It is commonly used by penetration testers, bug bounty hunters, and red teamers during the information-gathering phase.

## Task 1: Cloning GoSpider

I started by cloning the official GoSpider repository from GitHub.

```bash
git clone https://github.com/jaeles-project/gospider.git
```

## Task 2: Opening the GoSpider Directory

After cloning the repository, I moved into the GoSpider folder.

```bash
cd gospider
```

## Task 3: Attempting to Build GoSpider

I attempted to build GoSpider using the following command:

```bash
go build
```

The terminal showed that the `go` command was not installed, so Golang had to be installed before continuing.

## Task 4: Installing Golang

I installed the required Go package using:

```bash
sudo apt install gccgo-go
```

After confirming the installation, the required packages were downloaded and configured successfully.

## Task 5: Checking the Go Version

I verified the Go installation by running:

```bash
go version
```

The terminal displayed the installed Go version, confirming that the installation was complete.

## Task 6: Building the Repository Again

After installing Go, I attempted to build GoSpider again.

```bash
go build
```

The source build displayed dependency and compatibility errors. Because the repository could not be built successfully with the installed environment, I continued by downloading the precompiled Linux release from the official GoSpider GitHub Releases page.

## Task 7: Downloading the GoSpider Release

I opened the official GoSpider repository on GitHub and downloaded the latest available Linux x86_64 release package:

```text
gospider_v1.1.6_linux_x86_64.zip
```

The file was downloaded inside Kali Linux so it could be accessed from the terminal.

## Task 8: Extracting the ZIP File

I moved the downloaded release package into the GoSpider folder and extracted it using:

```bash
unzip gospider_v1.1.6_linux_x86_64.zip
```

The archive contained the GoSpider executable along with its license and README files.

## Task 9: Installing the GoSpider Executable

I gave execution permission to the GoSpider binary.

```bash
chmod +x gospider_v1.1.6_linux_x86_64/gospider
```

I then moved the executable to `/usr/local/bin/` so that GoSpider could be run from any terminal location.

```bash
sudo mv gospider_v1.1.6_linux_x86_64/gospider /usr/local/bin/
```

## Tasks 10: Running GoSpider

After completing the installation, I ran GoSpider against the website provided in the practical task.

```bash
gospider -s https://cust.edu.pk
```

GoSpider started crawling the target website and displayed discovered information in the terminal. The results included URLs, links, JavaScript resources, subdomains, robots.txt entries, and other endpoints found during the crawl.

I allowed the scan to continue until the crawling process was completed and reviewed the final results shown in the terminal.

## Features Observed

During this practical task, I observed the following GoSpider capabilities:

- Website crawling
- URL discovery
- Subdomain discovery
- JavaScript file discovery
- Endpoint extraction
- Link collection
- Robots.txt analysis
- Web reconnaissance support
- 
## Result

GoSpider was successfully downloaded, extracted, installed, and executed on Kali Linux. The practical helped me understand how a web spider can be used during reconnaissance to crawl a website and discover useful URLs, files, links, subdomains, and endpoints.
GoSpider was successfully downloaded, extracted, installed, and executed on Kali Linux. The practical helped me understand how a web spider can be used during reconnaissance to crawl a website and discover useful URLs, files, links, subdomains, and endpoints.
