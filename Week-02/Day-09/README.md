# Week 2 Day 9: CamPhish Practical

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I installed and tested CamPhish in Kali Linux to understand how social engineering tools request camera and location permissions.

The practical was performed only on my own device for educational purposes.

## Steps Performed

- Updated Kali Linux and installed the required dependencies
- Downloaded the CamPhish repository
- Opened the CamPhish folder
- Made the `camphish.sh` file executable
- Started the CamPhish tool
- Selected the tunnel and page template
- Opened the generated link on my own device
- Allowed camera and location permissions
- Checked the received location and camera results
- Verified the captured files inside the CamPhish folder

## Camera Issue

At first, the camera file was not received because Kali Linux was not detecting the webcam.

When I checked the camera devices, no `/dev/video` device was available.

I connected the webcam to the Kali virtual machine and checked again. After that, the following devices appeared:

`/dev/video0`  
`/dev/video1`

The camera was then detected successfully and the practical was completed.

## Result

CamPhish successfully received the test location information and camera file from my own authorized device.

The captured files were checked inside the CamPhish folder.

## Safety Note

This practical was performed only on my own laptop and camera.

No link was sent to another person, and no unauthorized device or personal information was accessed.

Sensitive details such as IP address, location coordinates and public tunnel links were hidden from the screenshots.

## Status

Completed
