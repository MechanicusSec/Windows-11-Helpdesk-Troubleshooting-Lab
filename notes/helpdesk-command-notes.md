# Helpdesk Command Notes

## Purpose

This file contains useful Windows helpdesk commands used during the Windows 11 Helpdesk Troubleshooting Lab.

The goal is to collect common commands in one readable reference so they can be reused during troubleshooting, documentation and verification work.

---

## System baseline commands

### winver

```powershell
winver
```

Purpose:

Opens the About Windows dialog and shows the Windows edition, version and OS build.

This is useful when confirming exactly what Windows version is running on a client computer.

---

### hostname

```powershell
hostname
```

Purpose:

Shows the computer name.

This is useful when confirming which machine is being investigated, especially when working with multiple virtual machines or support tickets.

---

### whoami

```powershell
whoami
```

Purpose:

Shows the currently logged-in user.

This is useful when confirming whether the correct user account is logged in and whether the technician is working in the expected context.

---

### Get-ComputerInfo

```powershell
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber, CsName
```

Purpose:

Shows selected Windows system information.

This command is useful for collecting operating system and computer name information in PowerShell.

Note:

PowerShell may show `WindowsProductName` as Windows 10 even when the system is Windows 11. In that case, `winver` and the OS build should be used as stronger evidence.

---

## Disk commands

### Get-PSDrive C

```powershell
Get-PSDrive C
```

Purpose:

Shows used and free space on the C: drive.

This is useful when investigating disk space issues.

---

### mkdir

```powershell
mkdir C:\Temp\HelpdeskDiskTest
```

Purpose:

Creates a temporary folder.

In this lab, it was used to create a safe test folder for disk troubleshooting.

---

### fsutil file createnew

```powershell
fsutil file createnew C:\Temp\HelpdeskDiskTest\testfile.bin 104857600
```

Purpose:

Creates a test file with a specific size.

In this lab, the command created a 100 MB file to safely simulate disk usage.

The number `104857600` means 100 MB in bytes.

---

### dir

```powershell
dir C:\Temp\HelpdeskDiskTest
```

Purpose:

Lists the contents of a folder.

This is useful for confirming that a test file or folder was created successfully.

---

### Remove-Item

```powershell
Remove-Item C:\Temp\HelpdeskDiskTest -Recurse -Force
```

Purpose:

Deletes a folder and its contents.

`-Recurse` means PowerShell also deletes everything inside the folder.

`-Force` allows PowerShell to remove items without extra prompts.

---

### Test-Path

```powershell
Test-Path C:\Temp\HelpdeskDiskTest
```

Purpose:

Checks whether a file or folder path exists.

If the result is `False`, the path does not exist.

This is useful after cleanup to confirm that the test folder was removed.

---

## Network commands

### ipconfig /all

```powershell
ipconfig /all
```

Purpose:

Shows detailed network configuration.

This includes IP address, subnet mask, default gateway, DNS servers, MAC address and adapter information.

---

### nslookup

```powershell
nslookup microsoft.com
```

Purpose:

Tests DNS resolution.

DNS resolution means checking whether a domain name can be translated into an IP address.

If this works, DNS is likely functioning.

---

### ping

```powershell
ping microsoft.com
```

Purpose:

Tests ICMP connectivity.

A failed ping does not always mean the network is down. Some servers block or ignore ping traffic.

In this lab, ping failed, but HTTP and HTTPS connectivity still worked.

---

### Test-NetConnection HTTP

```powershell
Test-NetConnection microsoft.com -CommonTCPPort HTTP
```

Purpose:

Tests TCP connectivity on port 80.

Port 80 is commonly used for HTTP web traffic.

This is useful when checking whether web traffic can reach a remote server.

---

### Test-NetConnection HTTPS

```powershell
Test-NetConnection microsoft.com -Port 443
```

Purpose:

Tests TCP connectivity on port 443.

Port 443 is commonly used for HTTPS web traffic.

This is often more useful than ping when testing whether web access works.

---

### ipconfig /flushdns

```powershell
ipconfig /flushdns
```

Purpose:

Clears the local DNS resolver cache.

This can help when a computer has old or incorrect DNS information stored locally.

---

## Windows Update and service commands

### start ms-settings:windowsupdate

```powershell
start ms-settings:windowsupdate
```

Purpose:

Opens the Windows Update page in Windows Settings.

This is useful when quickly navigating to update status, restart requirements and update options.

---

### Get-Service wuauserv

```powershell
Get-Service wuauserv
```

Purpose:

Checks the Windows Update service.

The Windows Update service is responsible for detecting, downloading and installing Windows updates.

---

### Get-Service bits

```powershell
Get-Service bits
```

Purpose:

Checks Background Intelligent Transfer Service.

BITS is used by Windows Update and other services to transfer files in the background.

---

### Get-Service cryptsvc

```powershell
Get-Service cryptsvc
```

Purpose:

Checks Cryptographic Services.

This service helps Windows verify signatures and certificates used by updates and system components.

---

### Get-Service msiserver

```powershell
Get-Service msiserver
```

Purpose:

Checks Windows Installer service.

This service is used when installing, modifying or removing software packages.

---

### Get-Service Spooler

```powershell
Get-Service Spooler
```

Purpose:

Checks the Print Spooler service.

The Print Spooler handles print jobs and printer communication.

If printers or print queues are not working, this is one of the first services to check.

---

## Event Viewer commands

### eventvwr.msc

```powershell
eventvwr.msc
```

Purpose:

Opens Event Viewer.

Event Viewer is used to investigate system, application and security logs.

---

### Get-WinEvent

```powershell
Get-WinEvent -LogName System -MaxEvents 5
```

Purpose:

Reads the five newest events from the System log.

This is useful for quickly checking recent system events from PowerShell.

---

## Local users and groups commands

### compmgmt.msc

```powershell
compmgmt.msc
```

Purpose:

Opens Computer Management.

Computer Management includes tools for local users, groups, services, disks and other administrative areas.

---

### Get-LocalUser

```powershell
Get-LocalUser
```

Purpose:

Lists local user accounts on the computer.

This is useful when checking what local accounts exist on a Windows client.

---

### Get-LocalGroup

```powershell
Get-LocalGroup
```

Purpose:

Lists local groups on the computer.

This is useful when reviewing local permission groups.

---

### Get-LocalGroupMember Administrators

```powershell
Get-LocalGroupMember Administrators
```

Purpose:

Lists members of the local Administrators group.

This is useful when checking which accounts have administrative privileges.

---

## Printer commands

### Get-Printer

```powershell
Get-Printer
```

Purpose:

Lists installed printers.

This is useful when checking whether Windows can see printers installed on the machine.

---

### Get-Service Spooler

```powershell
Get-Service Spooler
```

Purpose:

Checks Print Spooler status.

The Print Spooler should normally be running when troubleshooting printer issues.

---

## Useful Windows tools

### devmgmt.msc

```powershell
devmgmt.msc
```

Purpose:

Opens Device Manager.

Device Manager is used to review hardware devices, drivers and device errors.

---

### services.msc

```powershell
services.msc
```

Purpose:

Opens Services.

Services is used to inspect, start, stop and restart Windows background services.

---

### compmgmt.msc

```powershell
compmgmt.msc
```

Purpose:

Opens Computer Management.

Computer Management provides access to multiple administrative tools in one console.

---

### eventvwr.msc

```powershell
eventvwr.msc
```

Purpose:

Opens Event Viewer.

Event Viewer is used to review Windows logs and investigate errors, warnings and system events.

---

## Git commands

### git status

```powershell
git status
```

Purpose:

Shows the current Git state.

This tells you which files are changed, staged, untracked or ready to commit.

---

### git add

```powershell
git add README.md logbook.md notes/helpdesk-command-notes.md screenshots/screenshot-12a-helpdesk-command-notes-created.png
```

Purpose:

Stages files for the next commit.

Staging means telling Git which changed files should be included in the commit.

---

### git commit

```powershell
git commit -m "Add helpdesk command notes"
```

Purpose:

Creates a Git checkpoint with a message.

A commit records the current staged changes in the project history.

---

### git push

```powershell
git push
```

Purpose:

Uploads local commits to GitHub.

This makes the latest project version available in the remote repository.

---

## Notes

These commands were used as part of a Windows 11 helpdesk and junior sysadmin troubleshooting lab.

The commands support common support tasks such as:

* checking system information
* reviewing disk space
* testing network connectivity
* checking Windows Update services
* reviewing Event Viewer logs
* checking local users and groups
* troubleshooting printers
* documenting work with Git
