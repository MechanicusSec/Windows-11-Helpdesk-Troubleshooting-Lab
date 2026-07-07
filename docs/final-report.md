# Windows 11 Helpdesk Troubleshooting Lab — Final Report

## Project summary

The Windows 11 Helpdesk Troubleshooting Lab is a practical IT support and junior sysadmin portfolio project.

The project demonstrates common Windows 11 troubleshooting workflows using a safe local virtual machine environment. The lab focuses on realistic helpdesk tasks such as system baseline verification, network troubleshooting, disk space checks, Windows Update review, service troubleshooting, Event Viewer investigation, local users and groups review, printer troubleshooting simulation and documentation.

The goal of the project was to act as an IT support technician investigating common Windows 11 support issues and documenting the process clearly with screenshots, notes, PowerShell commands and Git history.

## Lab environment

| Component | Description |
| --- | --- |
| Host system | Windows workstation used for documentation, screenshots, Git and GitHub workflow |
| Lab system | Windows 11 virtual machine |
| Virtualization | VMware-based Windows 11 VM |
| Lab user | Local lab account |
| Documentation tools | VS Code and Markdown |
| Version control | Git and GitHub |
| Evidence | Screenshots, results notes, command notes and logbook entries |

## Completed troubleshooting areas

| Part | Area | Summary |
| --- | --- | --- |
| Part 1 | Project setup | Created the project structure, initialized Git and pushed the first version to GitHub. |
| Part 2 | Windows 11 baseline verification | Verified Windows version, hostname, user context, disk state, network configuration, TPM, Secure Boot, Device Manager and Windows Update status. |
| Part 3 | Network troubleshooting | Tested IP configuration, DNS resolution, ping behavior, HTTP connectivity, HTTPS connectivity and DNS cache flushing. |
| Part 4 | Disk space troubleshooting | Checked disk usage, created a safe 100 MB test file, reviewed Storage settings and confirmed cleanup. |
| Part 5 | Windows Update troubleshooting | Reviewed Windows Update status, update history, advanced options, optional updates, troubleshooter location and related services. |
| Part 6 | Windows service troubleshooting | Used Services and PowerShell to inspect, stop, start and verify the Print Spooler service. |
| Part 7 | Event Viewer investigation | Reviewed the System log, filtered warnings/errors, inspected event details and verified log access with PowerShell. |
| Part 8 | Local users and groups | Reviewed local users, local groups and Administrators group membership through Computer Management and PowerShell. |
| Part 9 | Printer troubleshooting simulation | Reviewed installed printers, opened a print queue, checked printer properties, restarted Print Spooler and verified printers with PowerShell. |
| Part 10 | Helpdesk command notes | Created a command reference file containing useful Windows helpdesk commands used during the lab. |
| Part 11 | Final report and GitHub polish | Created the final report and polished the project documentation. |

## Skills demonstrated

This project demonstrates the following practical helpdesk and junior sysadmin skills:

* Windows 11 troubleshooting.
* Windows Settings navigation.
* PowerShell verification.
* System baseline collection.
* Network configuration review.
* DNS troubleshooting.
* ICMP versus TCP connectivity comparison.
* Disk space investigation.
* Safe temporary file creation and cleanup.
* Windows Update review.
* Windows service management.
* Print Spooler troubleshooting.
* Event Viewer investigation.
* Windows System log review.
* Local account and group review.
* Local administrator membership review.
* Printer troubleshooting simulation.
* Screenshot evidence collection.
* Markdown documentation.
* Git and GitHub workflow.
* Privacy-aware public documentation.
* Final report writing.

## Tools used

| Tool or command | Purpose |
| --- | --- |
| VS Code | Used to edit Markdown documentation and manage project files. |
| PowerShell | Used for command-line verification and troubleshooting. |
| Windows Settings | Used to inspect system, update, storage and printer settings. |
| Services | Used to inspect and manage Windows services. |
| Event Viewer | Used to investigate Windows event logs. |
| Computer Management | Used to review local users and groups. |
| Device Manager | Used to review hardware and driver state. |
| Git | Used for local version control. |
| GitHub | Used to publish the project as portfolio evidence. |
| Markdown | Used to write the README, logbook, command notes and final report. |

## Key findings

### Baseline verification

The Windows 11 VM was documented before troubleshooting work began. This made it possible to understand the normal system state before investigating specific issues.

### Network troubleshooting

The lab demonstrated that a failed ping does not always mean a network outage. DNS resolution and TCP connectivity over HTTP and HTTPS worked even when ICMP ping timed out.

### Disk troubleshooting

The lab demonstrated safe disk testing by creating and removing a temporary 100 MB test file. This allowed disk usage changes and cleanup to be verified without touching real user data.

### Windows Update troubleshooting

The lab demonstrated a GUI-first update workflow. Windows Update status, update history, advanced options, optional updates and related services were reviewed.

### Service troubleshooting

The Print Spooler service was used as a practical example of Windows service troubleshooting. The service was inspected, stopped, started and verified.

### Event Viewer investigation

The System log was reviewed and filtered for important event levels. A network warning event was inspected, showing how Event Viewer findings should be interpreted with context instead of treated as automatic proof of an active issue.

### Local users and groups

Local user accounts, local groups and Administrators group membership were reviewed. This demonstrated a common support task for checking access and local privileges.

### Printer troubleshooting

Printer troubleshooting was simulated using Microsoft Print to PDF. This allowed printer settings, print queue review, printer properties and Print Spooler checks to be practiced without physical printer hardware.

### Command reference documentation

The lab includes a dedicated command notes file. This makes the project easier to review because useful commands are collected by topic instead of only appearing inside chronological lab entries.

## Evidence collected

The project includes several types of evidence:

* Screenshots stored in the `screenshots/` folder.
* Written troubleshooting results stored in the `results/` folder.
* Command reference notes stored in the `notes/` folder.
* A full logbook stored in `logbook.md`.
* A final report stored in `docs/final-report.md`.
* Git commit history showing project progress.

## Privacy and safety notes

This project was completed in a safe local lab environment.

No real user data, production systems, passwords, license keys, private company data or personal Microsoft account information were used.

Public documentation uses:

```text
C:\Users\*****
```

instead of exposing the real Windows username.

Screenshots should be reviewed before publishing to make sure they do not expose private host paths, personal account names, private files, license keys or unrelated personal information.

## Lessons learned

This lab showed that effective helpdesk troubleshooting requires both technical commands and clear documentation.

The work also showed the value of checking issues through the graphical interface first, because that is where many users experience problems. PowerShell was then used to confirm findings and collect clean technical evidence.

The project also reinforced the importance of screenshots, written notes and Git history when building a professional IT portfolio.

## Conclusion

The Windows 11 Helpdesk Troubleshooting Lab demonstrates practical desktop support and junior sysadmin troubleshooting skills in a safe local environment.

The project covers common Windows 11 support areas and documents the process clearly through screenshots, results notes, command references, a logbook and a final report.

This makes the project suitable as portfolio evidence for helpdesk, desktop support, IT technician and junior sysadmin roles.
