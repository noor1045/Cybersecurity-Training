# Mimikatz

Mimikatz is an open-source Windows security research tool developed by Benjamin Delpy (`gentilkiwi`).

It is commonly used by security professionals to study Windows authentication mechanisms, credentials, NTLM authentication and Kerberos security in authorized penetration-testing and lab environments.

> **Disclaimer:** Mimikatz must only be used in authorized penetration testing, security research, and controlled lab environments.

## Features


- Credential security testing
- Pass-the-Hash concepts
- Pass-the-Ticket concepts
- Kerberos ticket security
- Golden Ticket / Silver Ticket research
- Credential injection research
- Windows authentication security testing

## Requirements

The lab runs Mimikatz on Kali Linux using Wine.

## Install Wine

```bash
sudo apt install wine -y
```

Wait for Wine and its required dependencies to finish installing.

##  Download Mimikatz

Move to `/opt`:

```bash
cd /opt
```

Download the Mimikatz archive:

```bash
sudo wget https://github.com/gentilkiwi/mimikatz/releases/download/2.2.0-20220919/mimikatz_trunk.zip
```

Extract it:

```bash
sudo unzip mimikatz_trunk.zip -d mimikatz
```

Enter the directory:

```bash
cd mimikatz
```

##  Verify Downloaded Files

Check the 64-bit files:

```bash
ls /opt/mimikatz/x64
```

Check the 32-bit files:

```bash
ls /opt/mimikatz/Win32
```

The folders contain files such as:

```text
mimikatz.exe
mimidrv.sys
mimilib.dll
mimispool.dll
```

##  Start Mimikatz with Wine

Move into the 64-bit directory:

```bash
cd /opt/mimikatz/x64
```

Run:

```bash
wine mimikatz.exe
```

Wine may display initialization or compatibility messages during the first launch.

##  Successful Launch

After successful startup, the Mimikatz banner should appear.

Example information displayed includes:

```text
mimikatz 2.2.0
Benjamin DELPY gentilkiwi
```

The console prompt will appear as:

```text
mimikatz #
```

This confirms that the application has started.

##  Version Check

Inside the Mimikatz console:

```text
version
```

The manual shows version information including:

```text
mimikatz 2.2.0
Windows NT
```

Some compatibility-related messages may appear because the application is being executed through Wine.

##  Reopen Mimikatz

If the application has been closed, reopen the terminal and run:

```bash
cd /opt/mimikatz/x64
wine mimikatz.exe
```

Wait until the following prompt appears:

```text
mimikatz #
```

##  Debug Privilege Check

The manual demonstrates the following command inside the controlled lab environment:

```text
privilege::debug
```

This relates to Windows debug privileges and should only be used inside an authorized test environment.


## Troubleshooting

If Mimikatz does not start, verify that Wine is installed:

```bash
wine --version
```

Verify that the executable exists:

```bash
ls /opt/mimikatz/x64
```

Then reopen it:

```bash
cd /opt/mimikatz/x64
wine mimikatz.exe
```

Wine-related warnings can appear because Mimikatz is a Windows program being executed through a compatibility layer on Linux.

## Intended Use

Mimikatz is intended for:

- Authorized penetration-testing labs
- Windows authentication research
- Defensive security training
- Security demonstrations
- Controlled red-team exercises
- Understanding credential and Kerberos security

## Disclaimer

This repository documentation is provided for educational and authorized security-testing purposes only. Do not use Mimikatz against systems, accounts, or networks without explicit permission from the owner.
