# Windows 11 Helpdesk Troubleshooting Lab — Logbook

## 2026-07-06 — Part 1: Project setup

### Goal

Create the documentation structure for the Windows 11 Helpdesk Troubleshooting Lab.

### Work completed

* Created the main project folder.
* Created documentation folders.
* Created README.md.
* Created logbook.md.
* Created .gitkeep files so Git can track empty folders.
* Opened the project in VS Code.
* Initialized the local Git repository.
* Created the GitHub repository.
* Pushed the initial project structure to GitHub.
* Captured the initial project structure and Git status screenshots.

### Screenshot evidence

#### Initial project structure

![Initial project structure](screenshots/screenshot-01-project-structure.png)

#### Initial Git status

![Initial Git status](screenshots/screenshot-02-initial-git-status.png)

#### Initial push complete

![Initial push complete](screenshots/screenshot-03-initial-push-complete.png)

### Notes

This lab documents common Windows 11 helpdesk troubleshooting tasks in a safe local environment.

The project is designed for practical IT support, desktop support and junior sysadmin portfolio use.

---

## 2026-07-06 — Part 2: Windows 11 baseline verification

### Goal

Document the normal baseline state of the Windows 11 lab VM before creating or troubleshooting issues.

The purpose of this part was to confirm the operating system version, system identity, disk status, network configuration, TPM, Secure Boot, Device Manager state and Windows Update state.

### Work completed

* Verified Windows version using `winver`.
* Confirmed the VM is running Windows 11 Pro.
* Recorded Windows version and OS build information.
* Checked the computer name with `hostname`.
* Checked the current logged-in lab user with `whoami`.
* Checked C: drive disk usage with `Get-PSDrive C`.
* Reviewed network configuration with `ipconfig /all`.
* Verified TPM status with `Get-Tpm`.
* Verified Secure Boot status with `Confirm-SecureBootUEFI`.
* Reviewed Device Manager for obvious missing drivers or warning icons.
* Checked Windows Update status.
* Documented a pending security update restart.
* Restarted the VM to complete the update.
* Confirmed Windows Update showed the system as up to date after restart.
* Created a baseline results note in the results folder.

### Commands used

```powershell
winver
hostname
whoami
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber, CsName
Get-PSDrive C
ipconfig /all
Get-Tpm
Confirm-SecureBootUEFI
devmgmt.msc
start ms-settings:windowsupdate
```

### Command purpose

| Command | Purpose |
| --- | --- |
| `winver` | Opens the About Windows window and shows the Windows edition, version and build. |
| `hostname` | Shows the computer name. |
| `whoami` | Shows the currently logged-in user account. |
| `Get-ComputerInfo` | Retrieves Windows system information. |
| `Select-Object` | Filters command output to show only selected fields. |
| `Get-PSDrive C` | Shows used and free space on the C: drive. |
| `ipconfig /all` | Shows detailed network adapter, IP, gateway, DNS and DHCP information. |
| `Get-Tpm` | Shows TPM status and whether the TPM is present, ready, enabled and activated. |
| `Confirm-SecureBootUEFI` | Checks whether Secure Boot is enabled. |
| `devmgmt.msc` | Opens Device Manager for hardware and driver review. |
| `start ms-settings:windowsupdate` | Opens the Windows Update page in Settings. |

### Baseline findings

| Area | Result |
| --- | --- |
| Windows edition | Windows 11 Pro |
| Windows version | 25H2 shown in About Windows |
| OS build | 26200.8037 shown in About Windows |
| PowerShell build output | OS build 26200 shown by `Get-ComputerInfo` |
| Computer name | Lab VM hostname verified |
| User account | Local lab user verified |
| Disk status | C: drive checked and available free space confirmed |
| Network status | IP configuration, gateway and DNS reviewed |
| TPM status | TPM present, ready, enabled and activated |
| TPM manufacturer | VMware virtual TPM |
| Secure Boot | Enabled |
| Device Manager | No obvious warning icons or missing-driver issues observed |
| Windows Update before restart | Security update pending restart |
| Windows Update after restart | System showed "You're up to date" |
| Optional update | Preview update available after restart |

### Screenshot evidence

#### Windows version

![Windows 11 winver](screenshots/screenshot-04a-windows-11-winver.png)

#### System and disk baseline

![Windows 11 system and disk baseline](screenshots/screenshot-04b-windows-11-system-disk-baseline.png)

#### Network baseline

![Windows 11 network baseline](screenshots/screenshot-04c-windows-11-network-baseline.png)

#### TPM and Secure Boot

![TPM and Secure Boot check](screenshots/screenshot-04d-windows-11-tpm-secureboot-check.png)

#### Device Manager baseline

![Device Manager clean baseline](screenshots/screenshot-04e-device-manager-clean-baseline.png)

#### Windows Update before restart

![Windows Update baseline pending restart](screenshots/screenshot-04f-windows-update-baseline.png)

#### Windows Update after restart

![Windows Update after restart](screenshots/screenshot-04g-windows-update-after-restart.png)

### Results file

| File | Description |
| --- | --- |
| results/windows-11-baseline-results.txt | Contains a written summary of the Windows 11 baseline verification results. |

### Notes

The Windows 11 VM was verified as a working baseline system before troubleshooting scenarios were introduced.

Windows Update initially showed a pending restart for a security update. After restarting, Windows Update showed the system as up to date. An optional preview update was available, but this was not treated as a required baseline issue.

The lab project files, documentation and Git repository are maintained on the host machine, while troubleshooting checks are performed inside the Windows 11 VM.

---

## 2026-07-06 — Part 3: Network troubleshooting lab

### Goal

Practice basic Windows 11 network troubleshooting using PowerShell and standard helpdesk commands.

The purpose of this part was to check IP configuration, DNS resolution, ICMP ping behavior, HTTP connectivity, HTTPS connectivity and DNS cache flushing.

### Work completed

* Reviewed the Windows 11 VM network configuration with `ipconfig /all`.
* Tested DNS name resolution with `nslookup microsoft.com`.
* Tested ICMP connectivity with `ping microsoft.com`.
* Observed that ping to microsoft.com timed out.
* Tested HTTP connectivity with `Test-NetConnection microsoft.com -CommonTCPPort HTTP`.
* Confirmed HTTP TCP connectivity succeeded.
* Tested HTTPS connectivity with `Test-NetConnection microsoft.com -Port 443`.
* Confirmed HTTPS TCP connectivity succeeded.
* Flushed the local DNS resolver cache with `ipconfig /flushdns`.
* Created a network troubleshooting results note in the results folder.

### Commands used

```powershell
ipconfig /all
nslookup microsoft.com
ping microsoft.com
Test-NetConnection microsoft.com -CommonTCPPort HTTP
Test-NetConnection microsoft.com -Port 443
ipconfig /flushdns
```

### Command purpose

| Command | Purpose |
| --- | --- |
| `ipconfig /all` | Shows detailed network adapter, IP address, gateway, DNS and DHCP information. |
| `nslookup microsoft.com` | Tests DNS name resolution by resolving microsoft.com to an IP address. |
| `ping microsoft.com` | Tests ICMP connectivity and packet loss to microsoft.com. |
| `Test-NetConnection microsoft.com -CommonTCPPort HTTP` | Tests TCP connectivity to microsoft.com on port 80 for HTTP traffic. |
| `Test-NetConnection microsoft.com -Port 443` | Tests TCP connectivity to microsoft.com on port 443 for HTTPS traffic. |
| `ipconfig /flushdns` | Clears the local Windows DNS resolver cache. |

### Findings

| Test | Result |
| --- | --- |
| IP configuration | VM network configuration reviewed. |
| DNS lookup | microsoft.com resolved to an IP address. |
| Ping test | Ping timed out with 100% packet loss. |
| HTTP test | TCP connection to port 80 succeeded. |
| HTTPS test | TCP connection to port 443 succeeded. |
| DNS cache flush | DNS resolver cache flushed successfully. |

### Troubleshooting conclusion

The failed ping test did not indicate a full network outage.

Because DNS resolution worked and TCP connectivity succeeded on both HTTP and HTTPS ports, the most likely explanation is that ICMP ping traffic was blocked or ignored by the remote host or network path.

This shows why helpdesk technicians should not rely on ping alone when troubleshooting network issues.

### Screenshot evidence

#### Network configuration

![Network ipconfig baseline](screenshots/screenshot-05a-network-ipconfig-baseline.png)

#### DNS lookup

![Network DNS lookup](screenshots/screenshot-05b-network-dns-lookup.png)

#### Ping test

![Network ping test](screenshots/screenshot-05c-network-ping-test.png)

#### HTTP connectivity test

![Network HTTP connectivity test](screenshots/screenshot-05d-network-http-connectivity-test.png)

#### HTTPS connectivity test

![Network HTTPS connectivity test](screenshots/screenshot-05e-network-https-connectivity-test.png)

#### DNS cache flush

![Network DNS flush](screenshots/screenshot-05f-network-dns-flush.png)

### Results file

| File | Description |
| --- | --- |
| results/windows-11-network-troubleshooting-results.txt | Contains the written network troubleshooting findings and conclusion. |

### Notes

This part demonstrated an important helpdesk troubleshooting principle: a failed ping does not always mean the network connection is broken.

The VM could resolve DNS and connect over HTTP and HTTPS even though ICMP ping timed out.

---

## 2026-07-07 — Part 4: Disk space troubleshooting lab

### Goal

Practice basic Windows 11 disk space troubleshooting using PowerShell and Windows Storage settings.

The purpose of this part was to check C: drive usage, create a safe test file, confirm disk usage behavior, review graphical storage settings and clean up the test data.

### Work completed

* Checked C: drive disk space with `Get-PSDrive C`.
* Created a temporary test folder at `C:\Temp\HelpdeskDiskTest`.
* Created a 100 MB test file using `fsutil file createnew`.
* Confirmed the test file existed with `dir`.
* Checked disk space after creating the test file.
* Opened Windows Storage settings with `start ms-settings:storagesense`.
* Removed the temporary test folder with `Remove-Item`.
* Confirmed the folder was deleted with `Test-Path`.
* Checked final disk space after cleanup.
* Created a disk space troubleshooting results note in the results folder.

### Commands used

```powershell
Get-PSDrive C
mkdir C:\Temp\HelpdeskDiskTest
fsutil file createnew C:\Temp\HelpdeskDiskTest\testfile.bin 104857600
dir C:\Temp\HelpdeskDiskTest
Get-PSDrive C
start ms-settings:storagesense
Remove-Item C:\Temp\HelpdeskDiskTest -Recurse -Force
Test-Path C:\Temp\HelpdeskDiskTest
Get-PSDrive C
```

### Command purpose

| Command | Purpose |
| --- | --- |
| `Get-PSDrive C` | Shows used and free space on the C: drive. |
| `mkdir C:\Temp\HelpdeskDiskTest` | Creates a temporary folder for the disk test. |
| `fsutil file createnew C:\Temp\HelpdeskDiskTest\testfile.bin 104857600` | Creates a 100 MB test file to safely simulate disk usage. |
| `dir C:\Temp\HelpdeskDiskTest` | Lists the test folder contents and confirms the test file exists. |
| `start ms-settings:storagesense` | Opens Windows Storage settings for graphical disk usage review. |
| `Remove-Item C:\Temp\HelpdeskDiskTest -Recurse -Force` | Deletes the test folder and all contents inside it. |
| `Test-Path C:\Temp\HelpdeskDiskTest` | Checks whether the test folder still exists after cleanup. |

### Findings

| Test | Result |
| --- | --- |
| Initial disk check | C: drive usage and free space were reviewed. |
| Test folder creation | Temporary disk test folder was created successfully. |
| Test file creation | 100 MB test file was created successfully. |
| Disk check after file creation | Disk usage was checked again after creating the test file. |
| Storage settings review | Windows Storage settings were opened and reviewed. |
| Cleanup | Test folder and file were removed successfully. |
| Final disk check | Disk space was checked again after cleanup. |

### Troubleshooting conclusion

The Windows 11 VM disk space troubleshooting process was completed successfully.

A safe 100 MB test file was created to simulate disk usage, then removed to confirm cleanup. This demonstrated how a helpdesk technician can verify disk usage before and after cleanup activity.

### Screenshot evidence

#### Disk space before test

![Disk space before test](screenshots/screenshot-06a-disk-space-before.png)

#### Test file created

![Disk test file created](screenshots/screenshot-06b-disk-test-file-created.png)

#### Disk space after test file

![Disk space after test file](screenshots/screenshot-06c-disk-space-after-test-file.png)

#### Storage settings review

![Storage settings review](screenshots/screenshot-06d-storage-settings-review.png)

#### Disk space after cleanup

![Disk space after cleanup](screenshots/screenshot-06e-disk-space-after-cleanup.png)

### Results file

| File | Description |
| --- | --- |
| results/windows-11-disk-space-troubleshooting-results.txt | Contains the written disk space troubleshooting findings and conclusion. |

### Notes

This part demonstrated how to check disk space, safely simulate disk usage and clean up test data.

The test file was intentionally small and created only inside the lab VM.

---

## 2026-07-07 — Part 5: Windows Update troubleshooting lab

### Goal

Practice Windows Update troubleshooting using the normal Windows graphical interface first, followed by basic PowerShell service verification.

The purpose of this part was to learn where Windows Update settings are located, how to review update status, how to inspect update history and optional updates, and how to verify related services.

### Work completed

* Opened Windows Update through Settings.
* Reviewed the main Windows Update status page.
* Documented a restart-required state.
* Reviewed Update history.
* Reviewed Advanced options.
* Reviewed Optional updates.
* Located the Windows Update troubleshooter.
* Checked Windows Update-related services with PowerShell.
* Restarted the VM to complete the pending update.
* Checked Windows Update again after restart.
* Created a Windows Update troubleshooting results note in the results folder.
* Skipped the registry-based restart-required check intentionally to focus on GUI navigation and service verification.

### GUI paths used

```text
Start
→ Settings
→ Windows Update
```

```text
Start
→ Settings
→ Windows Update
→ Update history
```

```text
Start
→ Settings
→ Windows Update
→ Advanced options
```

```text
Start
→ Settings
→ Windows Update
→ Advanced options
→ Optional updates
```

```text
Start
→ Settings
→ System
→ Troubleshoot
→ Other troubleshooters
→ Windows Update
```

### PowerShell commands used

```powershell
Get-Service wuauserv
Get-Service bits
Get-Service cryptsvc
Get-Service msiserver
```

### Command purpose

| Command | Purpose |
| --- | --- |
| `Get-Service wuauserv` | Checks the Windows Update service. |
| `Get-Service bits` | Checks the Background Intelligent Transfer Service used for background downloads. |
| `Get-Service cryptsvc` | Checks Cryptographic Services, which help verify signatures and certificates. |
| `Get-Service msiserver` | Checks Windows Installer service status. |

### Findings

| Check | Result |
| --- | --- |
| Windows Update main page | Restart required state was observed. |
| Pending update | Secure Boot Allowed Signature Database (DB) update was pending restart. |
| Update history | Update history was reviewed. |
| Advanced options | Advanced update settings were reviewed. |
| Optional updates | Optional updates page was reviewed. |
| Troubleshooter | Windows Update troubleshooter location was identified. |
| Service check | Windows Update-related services were checked with PowerShell. |
| Restart | VM was restarted to complete the pending update. |
| After restart | Windows Update was reviewed again after restart. |

### Troubleshooting conclusion

The Windows Update troubleshooting process was completed successfully.

This part demonstrated how to start with the normal Windows Settings interface before using PowerShell for service verification. This is useful for helpdesk work because users usually describe problems from the graphical interface, not from command-line output.

### Screenshot evidence

#### Windows Update main status

![Windows Update main status](screenshots/screenshot-07a-windows-update-main-status.png)

#### Windows Update history

![Windows Update history](screenshots/screenshot-07b-windows-update-history.png)

#### Windows Update advanced options

![Windows Update advanced options](screenshots/screenshot-07c-windows-update-advanced-options.png)

#### Windows Update optional updates

![Windows Update optional updates](screenshots/screenshot-07d-windows-update-optional-updates.png)

#### Windows Update troubleshooter location

![Windows Update troubleshooter location](screenshots/screenshot-07e-windows-update-troubleshooter-location.png)

#### Windows Update services

![Windows Update services](screenshots/screenshot-07f-windows-update-services.png)

#### Windows Update after restart

![Windows Update after restart](screenshots/screenshot-07g-windows-update-after-restart.png)

### Results file

| File | Description |
| --- | --- |
| results/windows-11-update-troubleshooting-results.txt | Contains the written Windows Update troubleshooting findings and conclusion. |

### Notes

This part focused more on GUI navigation because helpdesk technicians often need to guide users through Settings before using command-line verification.

The registry-based restart-required check was skipped intentionally.
