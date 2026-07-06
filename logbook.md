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

| Screenshot | Description |
| --- | --- |
| screenshots/screenshot-01-project-structure.png | Shows the initial project folder structure in VS Code or File Explorer. |
| screenshots/screenshot-02-initial-git-status.png | Shows the initial Git status with untracked project files before the first commit. |
| screenshots/screenshot-03-initial-push-complete.png | Shows the repository after the initial push to GitHub. |

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

| Screenshot | Description |
| --- | --- |
| screenshots/screenshot-04a-windows-11-winver.png | Shows Windows 11 Pro version and OS build in the About Windows dialog. |
| screenshots/screenshot-04b-windows-11-system-disk-baseline.png | Shows hostname, current lab user, system build information and C: drive disk space. |
| screenshots/screenshot-04c-windows-11-network-baseline.png | Shows network configuration from `ipconfig /all`. |
| screenshots/screenshot-04d-windows-11-tpm-secureboot-check.png | Shows TPM status and Secure Boot verification. |
| screenshots/screenshot-04e-device-manager-clean-baseline.png | Shows Device Manager baseline review. |
| screenshots/screenshot-04f-windows-update-baseline.png | Shows Windows Update with a security update pending restart. |
| screenshots/screenshot-04g-windows-update-after-restart.png | Shows Windows Update after restart with the system up to date. |

### Results file

| File | Description |
| --- | --- |
| results/windows-11-baseline-results.txt | Contains a written summary of the Windows 11 baseline verification results. |

### Notes

The Windows 11 VM was verified as a working baseline system before troubleshooting scenarios were introduced.

Windows Update initially showed a pending restart for a security update. After restarting, Windows Update showed the system as up to date. An optional preview update was available, but this was not treated as a required baseline issue.

The lab project files, documentation and Git repository are maintained on the host machine, while troubleshooting checks are performed inside the Windows 11 VM.
