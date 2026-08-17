# Day 21 - OpenVAS

## Overview

OpenVAS is an open-source vulnerability scanner used to identify security vulnerabilities, misconfigurations, and potential security risks in systems and networks.

For this practical, OpenVAS/GVM was installed and configured on Kali Linux. During the setup verification, some components were configured successfully, but the vulnerability feed synchronization was incomplete, which prevented the GVM service from starting correctly.

---

## Setup Verification

After completing the OpenVAS setup, the following command was used to check whether all GVM components were configured correctly:

```bash
sudo gvm-check-setup
```

The check confirmed that several components were installed and working correctly, including:

* OpenVAS Scanner
* Notus Scanner
* Server CA certificate
* Redis server
* Scanner database settings
* MQTT server configuration
* OpenVAS plugin permissions

However, the setup check returned the following error:

```text
ERROR: The NVT collection is very small.
```

The suggested fix was:

```bash
sudo greenbone-feed-sync --type nasl
```

The setup verification then reported:

```text
ERROR: Your GVM-25.04.0 installation is not yet complete!
```

![GVM Setup Check](ss/01-gvm-check-setup.png)

---

## Starting GVM

After checking the setup, the GVM services were started using:

```bash
sudo gvm-start
```

The command displayed the Greenbone Security Assistant web interface address:

```text
https://127.0.0.1:9392
```

However, the `gvmd` service failed to start successfully.

The following error was displayed:

```text
Job for gvmd.service failed because the service did not take the steps required by its unit configuration.
```

Kali also suggested checking the service status using:

```bash
systemctl status gvmd.service
```

and:

```bash
journalctl -xeu gvmd.service
```

![GVM Start Error](ss/02-gvm-start-error.png)

---

## Issue Encountered

The OpenVAS/GVM installation could not be fully completed because the vulnerability feed was not properly synchronized.

The main issue reported by `gvm-check-setup` was:

```text
The NVT collection is very small.
```

Because the required vulnerability data was incomplete, the `gvmd.service` also failed when attempting to start GVM.

---

## Current Status

OpenVAS and its main components are installed on Kali Linux, but the setup is currently incomplete due to the vulnerability feed synchronization issue.

The Greenbone web interface was configured at:

```text
https://127.0.0.1:9392
```

but the GVM manager service could not start successfully.

This practical demonstrated the OpenVAS installation and configuration process as well as the troubleshooting information provided by Kali when the GVM setup is incomplete.

