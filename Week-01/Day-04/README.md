# Cybersecurity Training — Week 1, Day 4

## Task Title

Android Forensic Data Extraction and Analysis Using Andriller

## Task Objective

The objective of this task was to understand the basic process of Android mobile forensics.

For this practical, I installed and configured Andriller, connected an authorized Android device, performed a logical backup extraction, reviewed the extracted artifacts, and generated a forensic report.

The task helped me understand how investigators can collect and organize useful information from an Android device without manually searching through every file.

## What is Andriller?

Andriller is an Android forensic analysis tool used to extract, decode, and organize data from Android devices and previously acquired Android backups.

It can identify and process different types of mobile artifacts, including:

- Device information
- User accounts
- SMS and MMS records
- Call logs
- Contacts
- Browser information
- Application data
- Social media account references
- Timestamps
- Android backup files

Andriller can also generate structured reports that make the extracted information easier to review during an investigation.

## Purpose of Android Forensics

Android forensics is the process of collecting and examining data from an Android device.

The main purpose is to identify digital evidence that may help explain:

- Which accounts were used on the device
- Which applications were installed
- When certain activities occurred
- What communication records were available
- Whether important forensic artifacts were present
- How the device was configured

In a real investigation, this information may support incident response, cybercrime investigation, internal investigations, or law-enforcement work.

## Lab Environment

The following environment was used for this task:

- Host Operating System: Windows
- Python Version: Python 3.11
- Python Environment: Virtual environment
- Andriller Version: Andriller CE 3.6.3
- Android Data Source: Authorized Android mobile device
- Connection Method: USB
- Extraction Method: Logical backup extraction
- Output Directory: `C:\AndrillerLab\output\Day4`
- Report Format: HTML
- Documentation Platform: GitHub

## Python Environment Setup

My system already had Python 3.11 installed.

Instead of installing Andriller directly into the main Python environment, I created a separate virtual environment. This helped keep Andriller and its dependencies separate from other Python projects.

The working directory was created using:

bat
mkdir C:\AndrillerLab
cd /d C:\AndrillerLab


A virtual environment was then created using:

bat
py -3.11 -m venv env

The environment was activated using:

bat
env\Scripts\activate

After activation, the command prompt displayed the environment name before the path.

## Installing Andriller

With the virtual environment active, I upgraded pip using:

bat
python -m pip install --upgrade pip

I then installed Andriller using:

bat
pip install andriller -U

The installed package was checked using:

bat
pip show andriller

The installation completed successfully, and Andriller CE 3.6.3 was available in the virtual environment.

## Launching Andriller

I launched Andriller using:

bat
python -m andriller

The graphical interface opened successfully.

The main interface included the following options:

Extraction through USB
Parse extracted folder
Parse TAR backup
Parse Android Backup file
Output directory selection
Decoders
Application utilities
ADB tools
Report and log options

## Configuring the Output Directory

Before starting the extraction, I created a separate folder for the generated files and reports.

The folder structure was:

text
C:\AndrillerLab\
├── env\
└── output\
    └── Day4\

The selected Andriller output directory was:

text
C:\AndrillerLab\output\Day4

Keeping the output outside the Python environment helped keep the extracted data, reports, and application files organized.

## Preparing the Android Device

An authorized Android phone was used for this practical.

Before connecting the phone, Developer Options were enabled.

The process included:

1. Opening the phone settings
2. Finding the Build Number
3. Tapping the Build Number seven times
4. Confirming the phone password or PIN
5. Opening Developer Options
6. Enabling USB Debugging
7. Connecting the phone to the computer with a USB data cable
8. Allowing USB debugging when the phone displayed the authorization prompt

The phone remained unlocked during the extraction process.

## Device Connection

After connecting the phone, I opened the `Extraction (USB)` section in Andriller.

The device connection was checked using the `Check` option.

Andriller successfully detected the authorized Android device.

The device was connected with ADB shell-level access, which allowed Andriller to collect available logical information from the phone.

## Extraction Method

For this task, I used the Android Backup method.

The `Use AB method (ignore root)` option was selected before starting the extraction.

This method was chosen because it provides a logical extraction without requiring the phone to be rooted.

Logical extraction is safer for beginner training because it collects accessible data without attempting deeper physical access to the device storage.

## Starting the Extraction

After confirming the device connection and output location, I started the extraction.

Andriller displayed an instruction message asking me to:

1. Unlock the phone
2. Confirm the backup request on the Android device
3. Continue the extraction from the computer

The phone displayed a backup confirmation prompt.

After approving the request, Andriller began acquiring the available data.

The interface displayed the following status:

text
Acquiring data

The phone remained connected and unlocked until the extraction process was completed.

## Data Processing

After acquiring the available backup information, Andriller processed and organized the extracted data.

The tool generated a readable forensic report containing categories such as:

Device status
ADB permission level
Local and device time
Account information
Application references
Android package information
Social media application references
Device-related artifacts

The availability of individual artifacts depended on the Android version, application permissions, phone configuration, and backup restrictions.

## Forensic Artifacts Identified

The generated report contained useful Android forensic artifacts.

The report showed general categories such as:

Device serial information
Connection status
Shell permission
Device time
Local computer time
Configured Google accounts
WhatsApp account references
Social media application references
Installed application account entries
Android service information

For privacy reasons, personal email addresses, device identifiers, MAC addresses, and social media account IDs were not uploaded publicly to GitHub.

Only redacted screenshots and a general summary were used in the documentation.

## Generated Report

Andriller successfully generated an HTML forensic report.

The report was saved inside:

text
C:\AndrillerLab\output\Day4

The report presented the extracted Android artifacts in a structured table.

This made it easier to review the information without manually inspecting raw databases or backup files.

## Privacy and Data Protection

The report contained private information from the authorized Android device.

This included:

Email addresses
Device serial number
Wi-Fi MAC address
Application account names
Social media identifiers
Android account information

To protect privacy, I followed these precautions:

I did not upload the complete forensic report to GitHub.
Sensitive values were hidden or redacted from screenshots.
Only general artifact categories were described.
The phone used for the task was authorized.
The extraction was performed only for training purposes.
The original personal data was not publicly shared.

## Challenges Faced

During this task, I faced a few small challenges.

### Python Compatibility

Andriller officially supports older Python versions, but Python 3.11 was already installed on my system.

I tested the application inside a virtual environment, and Andriller installed and launched successfully.

Therefore, installing another Python version was not required.

### Output Folder Location

At first, I was unsure whether the output folder should be created inside the Python environment.

I learned that the output folder should remain outside the `env` directory.

The correct structure was:

text
C:\AndrillerLab\
├── env\
└── output\
    └── Day4\

### Developer Options

The location of the Build Number was different on the Android device.

I used the phone settings search option to locate the Build Number and enable Developer Options.

### USB Debugging

The phone needed to remain unlocked, and USB debugging authorization had to be accepted before Andriller could communicate with the device.

### Sensitive Information

The generated report contained personal account and device information.

I avoided uploading unredacted screenshots and documented only the general forensic findings.

## Important Forensic Practices

The following forensic practices were followed during this task:

Only an authorized Android device was used.
USB debugging was enabled with the device owner's permission.
A separate output folder was used for the extraction.
The extracted data was not modified manually.
Sensitive information was not uploaded publicly.
Every major step was documented.
The generated report was preserved locally.
Only redacted evidence screenshots were included in GitHub.
The original phone remained the primary source.
The analysis was performed on extracted data and the generated report.

## Tools Used

The following tools were used:

Windows
Python 3.11
Python Virtual Environment
Andriller CE 3.6.3
Android Debug Bridge
Authorized Android Device
USB Data Cable
File Explorer
GitHub

## Skills Learned

Through this task, I learned how to:

Install a Python-based forensic tool
Use a virtual Python environment
Configure Andriller
Enable Android Developer Options
Enable USB Debugging
Connect an authorized Android device through ADB
Perform a logical Android backup extraction
Review Android forensic artifacts
Generate a structured forensic report
Protect sensitive information during documentation
Organize forensic work on GitHub

## Result

Andriller was successfully installed and launched using Python 3.11.

An authorized Android device was connected through USB debugging.

A logical backup extraction was completed, and Andriller generated a structured forensic report containing device and account-related artifacts.

The report was saved locally, reviewed, and documented without exposing sensitive personal information.

## Task Status

Completed successfully.
