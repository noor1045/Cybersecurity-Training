# Day 21 - OWASP ZAP

## Overview

OWASP ZAP (Zed Attack Proxy) is an open-source security tool developed by the Open Web Application Security Project (OWASP).

It is widely used for penetration testing and web application security assessment. OWASP ZAP helps security testers identify vulnerabilities such as:

* SQL Injection
* Cross-Site Scripting (XSS)
* Insecure authentication/session flaws
* Directory traversal
* Misconfigurations

ZAP can work as both an intercepting proxy and an automated vulnerability scanner.

---

##  Install OWASP ZAP

First, the system package list was updated and OWASP ZAP was installed using:

```bash
sudo apt update
```

```bash
sudo apt install zaproxy -y
```



---

##  Run OWASP ZAP

OWASP ZAP was launched using the following command:

```bash
zaproxy
```



##  OWASP ZAP Interface

After launching, the OWASP ZAP interface was opened successfully.

The interface provides access to different security testing features and scanning options.


##  Dashboard

The OWASP ZAP dashboard was opened to access the available testing options.



## Automated Scan

The Automated Scan option was selected from the dashboard to begin automated vulnerability testing.


##  Automated Scan Dashboard

The Automated Scan dashboard was displayed where the target website could be configured for scanning.


##  Enter Target and Start Attack

The target URL was entered into OWASP ZAP and the Attack button was selected to start the automated scan.


---

##  Scan Process

OWASP ZAP started analyzing the target application and began the security scan process.


## Conclusion

OWASP ZAP was successfully installed and explored in Kali Linux.

The practical demonstrated how OWASP ZAP can be used for web application security assessment through its automated scanning feature and dashboard-based vulnerability testing.

