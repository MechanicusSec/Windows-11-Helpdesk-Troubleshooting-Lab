# Windows 11 Helpdesk Troubleshooting Lab

## Overview

Windows 11 Helpdesk Troubleshooting Lab is a practical IT support and junior sysadmin portfolio project focused on common Windows 11 troubleshooting tasks.

The lab covers baseline verification, network troubleshooting, disk space checks, Windows Update review, Windows services, Event Viewer investigation, local users and groups, printer troubleshooting simulation and final documentation.

This project uses a safe local lab environment only.

No real user data, production systems, passwords, private files or company devices are used.

## Scenario

A user reports several common Windows 11 support issues.

The goal of this lab is to act as an IT support technician and investigate the issues using Windows tools, PowerShell and structured documentation.

The project demonstrates how a helpdesk technician can collect baseline information, verify system health, investigate common problems and document the troubleshooting process clearly.

## Lab environment

| Component | Description |
| --- | --- |
| Host system | Windows workstation used for documentation, screenshots, Git and GitHub workflow |
| Lab system | Windows 11 virtual machine |
| Virtualization | VMware-based Windows 11 VM |
| Lab user | Local lab account |
| Documentation tools | VS Code, Markdown, Git and GitHub |
| Evidence | Screenshots and results notes |

## Completed parts

| Part | Topic | Status |
| --- | --- | --- |
| Part 1 | Project setup | Complete |
| Part 2 | Windows 11 baseline verification | Complete |
| Part 3 | Network troubleshooting | Complete |
| Part 4 | Disk space troubleshooting | Complete |
| Part 5 | Windows Update troubleshooting | Complete |
| Part 6 | Windows service troubleshooting | Complete |
| Part 7 | Event Viewer investigation | Planned |
| Part 8 | Local users and groups | Planned |
| Part 9 | Printer troubleshooting simulation | Planned |
| Part 10 | Helpdesk command notes | Planned |
| Part 11 | Final report and GitHub polish | Planned |

## Project structure

```text
Windows-11-Helpdesk-Troubleshooting-Lab/
├── docs/
├── notes/
├── results/
├── screenshots/
├── scripts/
├── logbook.md
└── README.md
```

## Current evidence

| Screenshot | Description |
| --- | --- |
| screenshots/screenshot-01-project-structure.png | Shows the initial project folder structure. |
| screenshots/screenshot-02-initial-git-status.png | Shows the initial Git status before the first commit. |
| screenshots/screenshot-03-initial-push-complete.png | Shows the initial GitHub push completion. |
| screenshots/screenshot-04a-windows-11-winver.png | Shows Windows 11 Pro version and OS build. |
| screenshots/screenshot-04b-windows-11-system-disk-baseline.png | Shows hostname, lab user, system build and disk baseline. |
| screenshots/screenshot-04c-windows-11-network-baseline.png | Shows baseline network configuration. |
| screenshots/screenshot-04d-windows-11-tpm-secureboot-check.png | Shows TPM and Secure Boot verification. |
| screenshots/screenshot-04e-device-manager-clean-baseline.png | Shows Device Manager baseline review. |
| screenshots/screenshot-04f-windows-update-baseline.png | Shows Windows Update pending restart state. |
| screenshots/screenshot-04g-windows-update-after-restart.png | Shows Windows Update after restart with the system up to date. |
| screenshots/screenshot-05a-network-ipconfig-baseline.png | Shows network adapter and IP configuration from `ipconfig /all`. |
| screenshots/screenshot-05b-network-dns-lookup.png | Shows DNS lookup test for microsoft.com. |
| screenshots/screenshot-05c-network-ping-test.png | Shows ping to microsoft.com timing out. |
| screenshots/screenshot-05d-network-http-connectivity-test.png | Shows successful HTTP TCP connectivity to microsoft.com on port 80. |
| screenshots/screenshot-05e-network-https-connectivity-test.png | Shows successful HTTPS TCP connectivity to microsoft.com on port 443. |
| screenshots/screenshot-05f-network-dns-flush.png | Shows the DNS resolver cache being flushed successfully. |
| screenshots/screenshot-06a-disk-space-before.png | Shows C: drive disk space before the disk test. |
| screenshots/screenshot-06b-disk-test-file-created.png | Shows the 100 MB disk test file created in the temporary test folder. |
| screenshots/screenshot-06c-disk-space-after-test-file.png | Shows disk space after creating the test file. |
| screenshots/screenshot-06d-storage-settings-review.png | Shows Windows Storage settings review. |
| screenshots/screenshot-06e-disk-space-after-cleanup.png | Shows final disk space after deleting the test folder. |
| screenshots/screenshot-07a-windows-update-main-status.png | Shows Windows Update main status with restart required. |
| screenshots/screenshot-07b-windows-update-history.png | Shows Windows Update history. |
| screenshots/screenshot-07c-windows-update-advanced-options.png | Shows Windows Update advanced options. |
| screenshots/screenshot-07d-windows-update-optional-updates.png | Shows Windows Update optional updates. |
| screenshots/screenshot-07e-windows-update-troubleshooter-location.png | Shows the Windows Update troubleshooter location. |
| screenshots/screenshot-07f-windows-update-services.png | Shows Windows Update-related services checked with PowerShell. |
| screenshots/screenshot-07g-windows-update-after-restart.png | Shows Windows Update after restarting the VM. |
| screenshots/screenshot-08a-print-spooler-service-running-gui.png | Shows Print Spooler running in the Services console. |
| screenshots/screenshot-08b-print-spooler-properties-running.png | Shows Print Spooler properties while running. |
| screenshots/screenshot-08c-print-spooler-service-stopped-gui.png | Shows Print Spooler stopped from the GUI. |
| screenshots/screenshot-08d-print-spooler-service-restored-gui.png | Shows Print Spooler restored from the GUI. |
| screenshots/screenshot-08e-print-spooler-powershell-verification.png | Shows PowerShell verification of the Print Spooler service. |

## Results

| File | Description |
| --- | --- |
| results/windows-11-baseline-results.txt | Written summary of Windows 11 baseline verification findings. |
| results/windows-11-network-troubleshooting-results.txt | Written summary of network troubleshooting checks, findings and conclusions. |
| results/windows-11-disk-space-troubleshooting-results.txt | Written summary of disk space troubleshooting checks and cleanup results. |
| results/windows-11-update-troubleshooting-results.txt | Written summary of Windows Update troubleshooting checks and findings. |
| results/windows-11-service-troubleshooting-results.txt | Written summary of Windows service troubleshooting checks and findings. |

## Skills demonstrated

This lab demonstrates:

* Windows 11 troubleshooting.
* PowerShell command usage.
* System baseline verification.
* Windows version and build verification.
* Disk space investigation.
* Disk space troubleshooting.
* Temporary file creation for testing.
* Windows Storage settings review.
* Safe cleanup validation.
* Network configuration review.
* DNS troubleshooting.
* ICMP versus TCP connectivity comparison.
* HTTP and HTTPS port testing.
* DNS cache flushing.
* Windows Update troubleshooting.
* Windows Settings navigation.
* Update history review.
* Optional updates review.
* Windows Update troubleshooter location.
* Windows service verification.
* Windows service troubleshooting.
* Services console navigation.
* Print Spooler service management.
* GUI-based service stop/start workflow.
* PowerShell service verification.
* TPM verification.
* Secure Boot verification.
* Device Manager review.
* Windows Update review.
* Restart and update completion validation.
* Technical documentation.
* Screenshot evidence collection.
* Git and GitHub project workflow.

## Tools and commands used

| Tool or command | Purpose |
| --- | --- |
| VS Code | Used to edit project documentation and manage files. |
| Git | Used for local version control. |
| GitHub | Used to publish the portfolio project. |
| PowerShell | Used to run Windows support and verification commands. |
| Windows Update Settings | Used to review update status, restart requirements and available updates. |
| Update history | Used to review installed update history. |
| Advanced options | Used to review additional Windows Update settings. |
| Optional updates | Used to review optional drivers, preview updates and non-critical updates. |
| Windows Update troubleshooter | Built-in troubleshooting tool for update-related problems. |
| `winver` | Shows Windows version and OS build information. |
| `hostname` | Shows the computer name. |
| `whoami` | Shows the current logged-in user. |
| `Get-ComputerInfo` | Retrieves Windows system information. |
| `Get-PSDrive C` | Shows C: drive disk usage. |
| `ipconfig /all` | Shows detailed network configuration. |
| `nslookup microsoft.com` | Tests DNS name resolution by resolving a domain name to an IP address. |
| `ping microsoft.com` | Tests ICMP connectivity and packet loss to a target. |
| `Test-NetConnection microsoft.com -CommonTCPPort HTTP` | Tests HTTP TCP connectivity on port 80. |
| `Test-NetConnection microsoft.com -Port 443` | Tests HTTPS TCP connectivity on port 443. |
| `ipconfig /flushdns` | Clears the local Windows DNS resolver cache. |
| `mkdir C:\Temp\HelpdeskDiskTest` | Creates a temporary folder for disk testing. |
| `fsutil file createnew C:\Temp\HelpdeskDiskTest\testfile.bin 104857600` | Creates a 100 MB test file to simulate disk usage. |
| `dir C:\Temp\HelpdeskDiskTest` | Lists the contents of the test folder. |
| `Remove-Item C:\Temp\HelpdeskDiskTest -Recurse -Force` | Deletes the temporary test folder and its contents. |
| `Test-Path C:\Temp\HelpdeskDiskTest` | Confirms whether the test folder still exists after cleanup. |
| `start ms-settings:storagesense` | Opens Windows Storage settings. |
| `Get-Service wuauserv` | Checks the Windows Update service. |
| `Get-Service bits` | Checks Background Intelligent Transfer Service. |
| `Get-Service cryptsvc` | Checks Cryptographic Services. |
| `Get-Service msiserver` | Checks Windows Installer service. |
| Services console | Used to view and manage Windows background services. |
| Print Spooler | Windows service used to manage print jobs and printer queues. |
| `services.msc` | Opens the Windows Services management console. |
| `Get-Service Spooler` | Checks the current status of the Print Spooler service. |
| `Get-Tpm` | Shows TPM status. |
| `Confirm-SecureBootUEFI` | Checks Secure Boot status. |
| `devmgmt.msc` | Opens Device Manager. |
| `start ms-settings:windowsupdate` | Opens Windows Update settings. |

## Key troubleshooting lessons

### Baseline verification

Before troubleshooting, the Windows 11 VM baseline was documented. This confirmed the operating system version, disk status, network configuration, TPM status, Secure Boot status, Device Manager state and Windows Update state.

### Network troubleshooting

Part 3 demonstrated that a failed ping does not always mean the network connection is broken.

In this lab, DNS resolution worked and TCP connectivity succeeded on HTTP port 80 and HTTPS port 443, even though ping to microsoft.com timed out. This showed that ICMP traffic was likely blocked or ignored while normal web connectivity still worked.

### Disk space troubleshooting

Part 4 demonstrated how to check disk space, safely simulate disk usage and confirm cleanup.

A temporary 100 MB test file was created in `C:\Temp\HelpdeskDiskTest`, disk space was checked before and after the file was created, Windows Storage settings were reviewed, and the test folder was removed. This showed how a helpdesk technician can validate disk usage and cleanup without touching real user data.

### Windows Update troubleshooting

Part 5 demonstrated a GUI-first Windows Update troubleshooting workflow.

The lab showed how to review the Windows Update main page, update history, advanced options, optional updates and the Windows Update troubleshooter location. PowerShell was then used to verify related services.

This reflects a practical helpdesk workflow: start where the user is, then use command-line tools for confirmation and deeper troubleshooting.

### Windows service troubleshooting

Part 6 demonstrated a GUI-first Windows service troubleshooting workflow.

The lab showed how to open the Services console, locate Print Spooler, inspect its properties, stop the service, start it again and verify the final state with PowerShell.

This reflects a practical helpdesk workflow: use the graphical tool to understand and manage the service, then use PowerShell to confirm the result.

## Privacy notes

This project does not include real user data, private passwords, license keys, personal Microsoft account information or production company data.

Local user paths are documented using:

```text
C:\Users\*****
```

instead of the real Windows username.

Screenshots should avoid exposing personal account names, private host paths, real passwords, license keys, private files or unrelated personal information.
