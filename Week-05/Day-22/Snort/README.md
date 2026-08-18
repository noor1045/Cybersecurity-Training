# Day 22 - Snort

## Overview

Snort is a powerful open-source Network Intrusion Detection and Prevention System (NIDS/NIPS).

It analyzes network traffic in real time, detects suspicious activities, and generates alerts or blocks malicious traffic.

Kali Linux includes Snort in its repository, making installation and setup convenient.

---

## Introduction

Snort is used for network security monitoring and intrusion detection. It works by analyzing packets and comparing network traffic against predefined rules.

The main functions of Snort include:

* Monitoring network traffic
* Detecting suspicious activities
* Generating security alerts
* Blocking malicious traffic in IPS mode

---

# Configuration

Snort uses configuration files and rules to detect threats.

The default configuration directory can be checked using:

```bash
ls /etc/snort/
```

Important configuration steps include:

* Defining network variables such as `HOME_NET` and `EXTERNAL_NET`
* Configuring rule paths
* Including rulesets such as local rules and community rules

---

# Writing Snort Rules

A Snort rule follows this format:

```
action protocol src_ip src_port -> dst_ip dst_port (options)
```

Example rule for detecting ICMP Ping:

```
alert icmp any any -> any any (msg:"ICMP Ping detected"; sid:1000001; rev:1;)
```

Rule explanation:

* `alert` → Action taken when a rule matches
* `icmp` → Protocol being monitored
* `any any` → Source IP and port
* `-> any any` → Destination IP and port
* `msg` → Alert message
* `sid` → Unique Snort ID

Rules are stored in:

```
/etc/snort/rules/local.rules
```

---

# Testing Configuration

Before running Snort, the configuration can be tested using:

```bash
sudo snort -c /etc/snort/snort.lua -T
```

This checks whether the configuration files and rules are correctly loaded.

---

# Running Snort in IDS Mode

Snort can run in Intrusion Detection System mode to monitor live network traffic.

Command:

```bash
sudo snort -c /etc/snort/snort.lua -i eth0
```

In IDS mode, Snort analyzes packets from the selected network interface and generates alerts based on configured rules.

---

# Reading Traffic from PCAP Files

Snort can analyze previously captured network traffic using PCAP files.

Command:

```bash
sudo snort -r capture.pcap -c /etc/snort/snort.lua
```

This allows security analysts to review recorded network activity and identify suspicious behavior.

---

# Snort as IPS (Inline Mode)

Snort can also work as an Intrusion Prevention System by blocking traffic when configured with a supported DAQ mode.

Command:

```bash
sudo snort -Q --daq nfq -c /etc/snort/snort.lua
```

Inline mode allows Snort to actively prevent malicious traffic instead of only detecting it.

---

# Logging and Output

Snort stores logs and alerts in:

```
/var/log/snort/
```

Common output formats include:

* Plain text logs
* Unified2 binary format for external tools such as Barnyard2

---

# Conclusion

Snort is an essential tool for network security monitoring and intrusion detection.

Through installation, configuration, rule writing, and traffic analysis, users can understand how malicious activities are detected at the packet level and how rules define which traffic should be flagged or blocked.

Learning Snort provides foundational skills required for threat detection, prevention, and incident response in professional cybersecurity environments.

