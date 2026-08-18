# Day 23 - Wazuh

## Overview

Wazuh is an open-source security platform used for security monitoring, threat detection, vulnerability detection, and incident response.

It provides capabilities such as:

* Security monitoring
* Log analysis
* Threat detection
* Endpoint monitoring
* Vulnerability assessment

Wazuh uses agents installed on systems to collect security-related information and send it to the Wazuh manager for analysis.

---

# Task 1 - Download Wazuh Installation Script

The Wazuh installation script was downloaded using:

```bash
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
```

---

# Task 2 - Generate Configuration Files

The installation script was used to generate the required configuration files:

```bash
sudo bash wazuh-install.sh --generate-config-files
```

During this process, Wazuh checked system requirements and prepared the installation configuration.

---

# Task 3 - Configure Wazuh Installation

The Wazuh installation script was executed with the configuration file:

```bash
sudo ./wazuh-install.sh --config-file config.yml
```

If permission issues occurred, executable permission was added:

```bash
chmod +x wazuh-install.sh
```

Then the installation command was executed again.

---

# Task 4 - Install Wazuh Components

The Wazuh installation process installed and configured required components including:

* Wazuh Indexer
* Wazuh Manager
* Filebeat
* Wazuh Dashboard

The installation completed successfully after generating certificates, configuring services, and starting required components.

---

# Task 5 - Credentials

After installation, Wazuh generated login credentials for accessing the dashboard.

Login details:

```text
IP Address:
127.0.0.1

Username:
admin
```

The generated password was used to access the Wazuh dashboard.

---

# Task 6 - Access Wazuh Dashboard

The Wazuh dashboard was accessed through the browser.

The dashboard was opened using:

```text
https://127.0.0.1
```

A security warning appeared because the dashboard uses a self-signed certificate.

---

# Task 7 - Accept Security Certificate

The browser certificate warning was bypassed by selecting:

```text
Accept the Risk and Continue
```

This allowed access to the Wazuh login page.

---

# Task 8 - Login to Wazuh Dashboard

The Wazuh dashboard was accessed using:

```text
IP:
127.0.0.1

Username:
admin
```

After successful authentication, the Wazuh interface was displayed.

---

# Task 9 - Wazuh Dashboard

After login, the Wazuh dashboard displayed security monitoring information including:

* Agent summary
* Security alerts
* Threat intelligence
* Vulnerability detection
* File integrity monitoring

---

# Task 10 - Add Agent

A new agent was added to Wazuh.

After adding the agent, it appeared as an active connection in the dashboard.

The connected agent information was displayed under the agents section.

---

# Task 11 - Install Wazuh Agent on Host System

When adding an agent, Wazuh provided installation commands.

These commands were executed on the host system using PowerShell.

The Wazuh agent service was started successfully after installation.

---

# Conclusion

Wazuh was successfully installed and configured as a security monitoring platform.

This practical demonstrated:

* Installing Wazuh components
* Accessing the Wazuh dashboard
* Configuring authentication
* Adding and connecting agents
* Monitoring endpoints through the Wazuh interface

Wazuh provides an effective solution for security monitoring, threat detection, and incident response.

