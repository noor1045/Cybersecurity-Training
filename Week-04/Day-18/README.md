# Week 04 – Day 18: Hakrawler

## Overview

In this practical, I worked with Hakrawler, a Golang-based web crawler used for discovering URLs, endpoints, JavaScript files, parameters, and hidden files within a website.

Hakrawler is useful during reconnaissance and security assessments because it quickly crawls a target domain and displays the discovered web resources directly in the terminal.

## Installing Hakrawler with Go

I first attempted to install Hakrawler using the Go installation command:

```bash
go install github.com/hakluke/hakrawler@latest
```

The required packages started downloading, but the installation ended with an internal compiler error and segmentation fault. I documented the output and continued with the next steps shown in the practical.

## Configuring the Go Binary Path

I added the Go binary directory to the system PATH using:

```bash
export PATH=$PATH:$(go env GOPATH)/bin
```

This command allows programs installed through Go to be accessed directly from the terminal.

## Checking and Installing Hakrawler

I attempted to run Hakrawler against the provided website:

```bash
hakrawler -url https://cust.edu.pk
```

The terminal showed that the Hakrawler command was not available, so I installed the package through the Kali Linux package manager:

```bash
sudo apt install hakrawler
```

After confirming the installation, Hakrawler and its required package were installed successfully.

## Running the Hakrawler Scan

I started the web crawl using the command provided in the practical:

```bash
echo https://cust.edu.pk | hakrawler
```

Hakrawler began crawling the target website and displayed the discovered resources in the terminal.

The output included different website locations such as:

- Web pages
- URLs
- JavaScript files
- Documents
- Images
- Website assets
- Parameters
- Internal endpoints

## Reviewing the Results

I allowed the scan to continue until Hakrawler completed crawling the website and the terminal prompt appeared again.

The results showed multiple internal pages, files, scripts, media resources, and other links discovered from the target domain.

## Commands Used

```bash
go install github.com/hakluke/hakrawler@latest
export PATH=$PATH:$(go env GOPATH)/bin
hakrawler -url https://cust.edu.pk
sudo apt install hakrawler
echo https://cust.edu.pk | hakrawler
```
## Result
Hakrawler was successfully installed and used to crawl the provided website. This practical helped me understand how a web crawler can be used during reconnaissance to discover URLs, files, scripts, parameters, and hidden endpoints within a domain.

## Disclaimer
This practical was completed only for educational purposes and authorized security testing.

This practical was completed only for educational purposes and authorized security testing.
