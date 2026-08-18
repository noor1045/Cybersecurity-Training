# Day 21 - Responder

## Overview

Responder is a powerful penetration testing tool available in Kali Linux. It is used for LLMNR (Link-Local Multicast Name Resolution), NBT-NS (NetBIOS Name Service), and MDNS (Multicast DNS) poisoning attacks.

Responder listens on a network and responds to broadcast name resolution requests with its own IP address, which can trick systems into sending authentication hashes.

These captured hashes can later be analyzed and cracked to recover plaintext passwords.

---

## Key Use Cases

Responder can be used for:

* Capturing NTLMv1/NTLMv2 hashes
* SMB and HTTP authentication relay attacks
* Enumerating network services
* Supporting privilege escalation during internal penetration testing

---

## Features of Responder

### 1. Poisoning Protocols

Responder supports:

* LLMNR
* NBT-NS
* MDNS

### 2. Hash Capturing

It can capture:

* NTLMv1 hashes
* NTLMv2 hashes
* SMB authentication hashes

### 3. Authentication Relaying

Responder can forward authentication attempts to other services.

### 4. Modular Design

It supports multiple listeners including:

* SMB
* HTTP
* FTP
* LDAP

### 5. Integration

Captured hashes can be used with tools such as:

* John the Ripper
* Hashcat

---

# Tasks

##  Check Responder Installation

Responder is pre-installed in most Kali Linux versions.

The installation was verified using:

```bash id="2m9i9f"
responder -h
```


##  Locate Responder Directory

Responder directory was accessed using:

```bash id="j72z8v"
cd /usr/share/responder
```


##  Run Responder

Responder was started on the network interface:

```bash id="tx7qv5"
sudo responder -I eth0
```

##  Analyze Captured Data

During execution, Responder captured network name resolution requests.

### Poisoned Name Resolution Traffic

Multiple:

* MDNS
* LLMNR
* NBT-NS

requests showed that Kali was responding to broadcast requests from other hosts on the network.



## Conclusion

Responder was successfully explored in Kali Linux.

The practical demonstrated:

* Checking Responder availability
* Running Responder on a network interface
* Monitoring LLMNR, NBT-NS, and MDNS traffic
* Capturing NTLMv2 authentication hashes
* Performing hash analysis

Responder is an important tool for internal penetration testing and network security assessments.

