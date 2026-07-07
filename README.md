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
| Part 4 | Disk space troubleshooting | Planned |
| Part 5 | Windows Update troubleshooting | Planned |
| Part 6 | Windows service troubleshooting | Planned |
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

## Results

| File | Description |
| --- | --- |
| results/windows-11-baseline-results.txt | Written summary of Windows 11 baseline verification findings. |
| results/windows-11-network-troubleshooting-results.txt | Written summary of network troubleshooting checks, findings and conclusions. |

## Skills demonstrated

This lab demonstrates:

* Windows 11 troubleshooting.
* PowerShell command usage.
* System baseline verification.
* Windows version and build verification.
* Disk space investigation.
* Network configuration review.
* DNS troubleshooting.
* ICMP versus TCP connectivity comparison.
* HTTP and HTTPS port testing.
* DNS cache flushing.
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

## Privacy notes

This project does not include real user data, private passwords, license keys, personal Microsoft account information or production company data.

Local user paths are documented using:

```text
C:\Users\*****
```

instead of the real Windows username.

Screenshots should avoid exposing personal account names, private host paths, real passwords, license keys, private files or unrelated personal information.
