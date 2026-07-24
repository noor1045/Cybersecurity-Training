# Week 2 Day 8: Camera Permission Awareness Lab

## Student Details

Name: Noor E Eman  
Registration Number: BCS233016  
Course: Cybersecurity Training  

## Task Overview

In this task, I learned how websites request camera permission from a browser.

The original task was related to CamPhish, which shows how phishing pages may request camera access from a user. For safety, I performed the practical only on my own Kali Linux system using a local test page.

## Purpose

The purpose of this task was to understand how browser camera permissions work and why users should not allow camera access on unknown websites.

I also learned how phishing pages may try to convince users to select Allow and how this permission can create privacy risks.

## Local Test Page

I created a simple HTML page named `index.html`.

The page included two buttons:

- Test Camera Permission
- Stop Camera

I started the local server using:

`python3 -m http.server 8080`

Then I opened the page in Firefox using:

`http://127.0.0.1:8080`

The localhost address was used so the test remained limited to my own Kali Linux machine.

## Camera Preview Issue

At first, the camera preview did not work.

The page showed the following message:

`Camera permission was denied or the camera is unavailable.`

The issue happened because the webcam was not properly connected to the Kali Linux virtual machine and Firefox had not granted camera permission to the local page.

To solve the issue, I connected the webcam to Kali Linux, opened the Firefox camera permission settings, confirmed that new camera requests were not blocked, refreshed the page and clicked the Test Camera Permission button again.

When Firefox asked for camera permission, I selected Allow.

After completing these steps, the camera preview worked successfully.

## Result

The local page successfully requested camera permission from Firefox.

After permission was allowed, the camera preview appeared on the page. I then used the Stop Camera button and closed the browser page to stop the camera.

The test page did not save, upload or send any photo or video. It was only used locally to understand browser camera permissions.

## Screenshots

The following screenshots were taken during the practical:

- 01-local-server-running.png
- 02-camera-permission-request.png
- 03-camera-permission-denied.png
- 04-local-camera-preview.png

## What I Learned

From this task, I learned that camera permission is sensitive and should only be allowed on trusted websites.

A website normally requires user permission before accessing the camera. However, phishing pages may try to trick users into selecting Allow.

Users should always check the website address before allowing access to their camera, microphone or location.

## Safety Note

This practical was performed only on my own Kali Linux system in a controlled local environment.

No link was sent to another person and no third-party camera, photo or location information was collected.

## Status

Completed
