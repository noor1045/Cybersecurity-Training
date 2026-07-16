# Cybersecurity Training — Week 1, Day 2

## Task Objective
The purpose of this task was to understand how digital evidence is copied and verified during a forensic investigation.
For this practical, I used Guymager to create a forensic image of a separate 2 GB virtual hard disk. I used a virtual disk instead of a physical USB drive.

## What is Guymager?
Guymager is a digital forensic imaging tool used to create a bit-by-bit copy of a storage device.
A normal copy usually copies visible files only. A forensic image copies the complete storage device, which may include existing files, deleted data, partitions, and unused disk space.
Guymager supports forensic image formats such as:
- EWF/E01
- Raw image
- AFF
It also records case information and calculates hash values to help confirm that the forensic image has not been changed.

## Lab Setup
The following setup was used for this task:
- Operating System: Kali Linux
- Virtualization Platform: Oracle VirtualBox
- Forensic Imaging Tool: Guymager
- Source Device: Separate 2 GB virtual hard disk
- Source Device Name: `/dev/sdb`
- Main Kali Linux Disk: `/dev/sda`
- Image Format: EWF/E01
- Hash Algorithm: MD5
- Image Directory: `/home/noor/Forensic/Case001`
- Image Filename: `Day2VirtualDisk.E01`

## Creating the Virtual Evidence Disk
I first powered off the Kali Linux virtual machine and added a separate 2 GB virtual hard disk through the VirtualBox storage settings.
After starting Kali Linux, I checked the available storage devices using:
bash
lsblk -o NAME,SIZE,TYPE,FSTYPE,MOUNTPOINTS
The output showed:
- `/dev/sda` as the main Kali Linux disk
- `/dev/sdb` as the new 2 GB evidence disk
I checked the device name and size carefully before continuing so that I did not modify the main Kali Linux disk.

## Partitioning the Evidence Disk
I created a partition on the 2 GB evidence disk using the following commands:
bash
sudo parted /dev/sdb --script mklabel msdos
sudo parted /dev/sdb --script mkpart primary ext4 1MiB 100%
sudo partprobe /dev/sdb
After partitioning, `/dev/sdb1` appeared as the new partition.

## Formatting and Mounting the Evidence Disk
I formatted the partition with the ext4 filesystem and assigned it the label `DAY2_EVIDENCE`.
bash
sudo umount /dev/sdb1
sudo mkfs.ext4 -L DAY2_EVIDENCE /dev/sdb1
sudo mkdir -p /mnt/day2disk
sudo mount /dev/sdb1 /mnt/day2disk
I checked the filesystem, label, and mount point using:
bash
lsblk -o NAME,SIZE,TYPE,FSTYPE,LABEL,MOUNTPOINTS

## Creating Sample Evidence Files
I added sample files to the evidence disk so that the forensic image contained some test data.
bash
echo "Week 1 Day 2 forensic imaging test" | sudo tee /mnt/day2disk/evidence-note.txt
date | sudo tee /mnt/day2disk/created-time.txt
sudo mkdir -p /mnt/day2disk/Documents
echo "This is a sample investigation document." | sudo tee /mnt/day2disk/Documents/investigation-note.txt
I checked the files using:
bash
ls -lR /mnt/day2disk
The evidence disk contained:
- `evidence-note.txt`
- `created-time.txt`
- `Documents/investigation-note.txt`

## Preparing the Source Device
Before creating the forensic image, I saved all pending data and unmounted the source disk.
bash
sync
sudo umount /mnt/day2disk
The source partition was kept unmounted during the acquisition to reduce the risk of changing the evidence data.

## Installing Guymager
I installed Guymager and the EWF command-line tools using:
bash
sudo apt update
sudo apt install guymager ewf-tools libewf2 -y
I checked the installation using:
bash
which guymager
which ewfverify
## Starting Guymager

I opened Guymager with administrative privileges using:
bash
sudo guymager
Guymager displayed both virtual disks:

- `/dev/sda` — approximately 26.8 GB
- `/dev/sdb` — approximately 2.1 GB

I selected only `/dev/sdb`, which was the separate evidence disk.

## Case Information
I entered the following information in Guymager:
- Case Number: `CASE-001`
- Evidence Number: `VDISK-001`
- Examiner: `Noor`
- Description: `Virtual disk forensic acquisition`
- Notes: `Week 1 Day 2 Guymager practical`

## Acquisition Settings
I used the following acquisition settings:
- File Format: Expert Witness Format
- Output Image: `Day2VirtualDisk.E01`
- Target Directory: `/home/noor/Forensic/Case001`
- MD5 Hash Calculation: Enabled
- Verify Image After Acquisition: Enabled

After confirming the source device and destination folder, I started the acquisition.

Guymager successfully created a forensic image of the complete 2 GB virtual evidence disk.

## Checking the E01 Metadata
After the acquisition was completed, I opened the image directory:
bash
cd ~/Forensic/Case001
I checked the image metadata using:
bash
ewfinfo Day2VirtualDisk.E01
The output displayed:

- Case number
- Evidence number
- Examiner name
- Description
- Acquisition date
- Operating system
- Guymager version
- Source device model
- Source device serial number
- Media size
- MD5 hash

## Verifying the Forensic Image
I verified the integrity of the E01 image using:
bash
ewfverify Day2VirtualDisk.E01
The verification completed successfully. This confirmed that the forensic image was not corrupted or changed after acquisition.

## Hash Information
The MD5 hash recorded for the forensic image was:
text
0e8d5e14c58fd249a80b8c793061273f
A hash works like a digital fingerprint. If the forensic image changes, its hash value will also change.

## Challenges Faced
During the task, I faced a few small issues:
- The evidence disk was mounted when I first tried to format it.
- I unmounted `/dev/sdb1` before creating the filesystem.
- I typed `data` instead of the `date` command while creating a sample file.
- I initially tried to open the E01 image from the wrong directory.
- After moving to the correct `~/Forensic/Case001` directory, `ewfinfo` worked successfully.
These issues were corrected without affecting the final forensic image.

## Important Safety Measures
The following safety measures were followed:
- A separate virtual disk was used as the evidence source.
- The main Kali Linux disk `/dev/sda` was not selected.
- The evidence disk was identified by its device name and size.
- The source partition was unmounted before acquisition.
- The forensic image was saved to a separate destination.
- Hash calculation and verification were enabled.
- The source disk was not modified during the acquisition.

## Screenshots
The practical screenshots are available in the `Screenshots` folder.

### Virtual Evidence Disk Detected
![Virtual Evidence Disk](Screenshots/02-virtual-disk-detected.png)

### Evidence Disk Partitioned
![Evidence Disk Partitioned](Screenshots/03-evidence-disk-partitioned.png)

### Evidence Disk Formatted
![Evidence Disk Formatted](Screenshots/04-evidence-disk-formatted.png)

### Sample Evidence Files
![Sample Evidence Files](Screenshots/05-test-evidence-files.png)

### Guymager Device List
![Guymager Device List](Screenshots/08-guymager-device-list.png)

### Acquisition Settings
![Acquisition Settings](Screenshots/09-acquisition-settings.png)

### Acquisition Completed
![Acquisition Completed](Screenshots/11-acquisition-completed.png)

### E01 Metadata
![E01 Metadata](Screenshots/12-ewfinfo-metadata.png)

### E01 Verification
![E01 Verification](Screenshots/13-ewfverify-success.png)

## Tools Used
- Oracle VirtualBox
- Kali Linux
- Guymager
- ewf-tools
- Linux Terminal
- GitHub

## Result
The 2 GB virtual evidence disk was successfully imaged using Guymager.

The forensic image was saved in EWF/E01 format. The case metadata and MD5 hash were recorded correctly, and the image integrity was successfully verified using `ewfverify`.

## Task Status
Completed successfully.


Completed successfully.
