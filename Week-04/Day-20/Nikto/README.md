# Day 20 - Nikto

## Overview

Nikto is an open-source web server scanner used to identify potential vulnerabilities and misconfigurations in web servers. It performs different security checks to detect outdated software versions, dangerous files or scripts, missing security headers, information disclosure, and other possible security issues.

For this practical, Nikto was used to perform a vulnerability assessment of the target domain `cust.edu.pk`.

---

## Step 1 - Open Nikto

Nikto was opened from the Kali Linux application menu.

![Open Nikto](ss/01-open-nikto.png)

---

## Step 2 - View Nikto Help

The help menu was checked to review the available Nikto options and commands.

```bash
nikto --help
```

![Nikto Help](ss/02-nikto-help.png)

---

## Step 3 - Basic Web Server Scan

A basic Nikto scan was performed against the target domain.

```bash
nikto -h cust.edu.pk
```

The scan provided information about the target server and identified several possible security issues and exposed resources.

![Basic Nikto Scan](ss/03-basic-scan.png)

---

## Step 4 - Database Check

Nikto's database files were checked for syntax errors and duplicate test IDs.

```bash
nikto -h cust.edu.pk -dbcheck
```

The command checked the different Nikto databases and plugins used during vulnerability scanning.

![Nikto Database Check](ss/04-database-check.png)

---

## Step 5 - SSL Detection and Verbose Output

An HTTPS scan was performed on port `443` with SSL detection and verbose output enabled.

```bash
nikto -h https://cust.edu.pk -p 443 -ssl -Display V
```

Verbose mode displayed detailed information while Nikto initialized its plugins and performed the scan.

![SSL Verbose Scan](ss/05-ssl-verbose-scan.png)

---

## Step 6 - Save Scan Results

The Nikto scan results were saved in both HTML and TXT formats.

### HTML Output

```bash
nikto -h https://cust.edu.pk -o cust_scan.html -Format html
```

### TXT Output

```bash
nikto -h https://cust.edu.pk -o cust_scan.txt -Format txt
```

Saving the output makes it easier to review and document the vulnerability assessment results.

![Save Scan Output](ss/06-save-output.png)

---

## Step 7 - Vulnerability Assessment Results

The Nikto assessment identified several findings ranging from security misconfigurations to information disclosure issues.

### 1. Missing X-Content-Type-Options Header

**Affected resource:**

```text
/t3v70N6c.conf
```

**Issue:**
The response from this file does not include the `X-Content-Type-Options` security header.

**Risk:**
Browsers may attempt to sniff the content type, which can increase the risk of Cross-Site Scripting attacks.

**Recommendation:**

```text
X-Content-Type-Options: nosniff
```

---

### 2. Publicly Accessible Database Connection File

**Affected resource:**

```text
/pccsmysqladm/incs/dbconnect.inc
```

**Issue:**
The database connection file is publicly accessible and may contain sensitive credentials or configuration information.

**Risk:**
This may result in database credential disclosure or exposure of server-side configuration details.

**Recommendation:**

* Remove the file from public access.
* Restrict access to sensitive configuration files.

Example restriction:

```apache
<FilesMatch "dbconnect\.inc">
Order allow,deny
Deny from all
</FilesMatch>
```

---

### 3. IP Disclosure

An IP address was found through the `__cf_bm` / `set-cookie` header.

```text
1.0.1.1
```

**Risk:**
Exposed IP information may assist with network mapping and reconnaissance.

**Recommendation:**
Avoid exposing unnecessary internal or infrastructure-related IP information through HTTP headers or cookies.

---

### 4. Missing X-Frame-Options Header

**Issue:**
The website does not include the `X-Frame-Options` security header.

**Risk:**
The website may be vulnerable to UI redress or clickjacking attacks.

**Recommendation:**

```text
X-Frame-Options: DENY
```

---

### 5. Cloudflare Debug Endpoint Exposed

**Affected resource:**

```text
/cdn-cgi/trace
```

**Issue:**
The endpoint returns debugging information such as IP address, Cloudflare location, TLS details, and other environment information.

**Risk:**
This information may assist with fingerprinting and network reconnaissance.

**Recommendation:**
Disable or restrict access to the endpoint where possible.

---

### 6. Software Disclosure

**Affected resource:**

```text
/license.txt
```

**Issue:**
The file reveals information about the software platform being used, which appears to be WordPress.

**Risk:**
Software disclosure can help an attacker identify platform-specific vulnerabilities.

**Recommendation:**
Remove the file or prevent public access to it.

![Nikto Findings](ss/07-nikto-findings.png)

---

## Conclusion

Nikto successfully scanned the target web server and identified several security-related findings, including missing HTTP security headers, information disclosure, exposed files, and publicly accessible endpoints.

This practical demonstrated how Nikto can be used to assess a web server, perform SSL-based scans, verify its vulnerability databases, save scan results in different formats, and review findings for possible security improvements.

