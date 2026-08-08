# TCM Security - Practical SOC Analyst Associate

## Prerequisites

### VirtualBox

**Sources**

- VirtualBox → `https://www.virtualbox.org/wiki/Downloads`
- Microsoft Visual C++ Redistributable Package → `https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist` → X64 Architecture

**Customization**

- File → Preferences → Expert → Input → Virtual Machine → Host Key Combo → `Right Alt`

### Windows

**Source**

- Windows Evaluation Center → `https://www.microsoft.com/en-us/evalcenter/download-windows-11-enterprise`

**Specifications**

- Base Memory → `4096 MB`
- Number of CPUs → `2`
- Disk Size → `60 GB`
- Enable UEFI → `Use EFI`

**Installation**

- Skip Microsoft Sign in → `Domain join instead`
- File Explorer → View → Show → `File name extensions` / `Hidden items`
- Devices → Insert Guest Additions CD Image... → CD Drive (D:) VirtualBox Guest Additions → `VBoxWindowsAdditions-amd64.exe`
- View → `Full-screen Mode`
- Devices → Shared Clipboard → `Bidirectional`
- Machine → `Take Snapshot...`

**Configuration**

- Windows Security → Virus & threat protection → Virus & threat protection settings → Manage settings → `Turn Off Tamper Protection`
- Windows PowerShell → Run as administrator
- Disable real-time protection → `Set-MpPreference -DisableRealtimeMonitoring $true`
- Disable network files scanning → `Set-MpPreference -DisableScanningNetworkFiles $true`
- Disable first sight blocking → `Set-MpPreference -DisableBlockAtFirstSeen $true`
- Disable Windows Defender AntiSpyware → `reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f`
- Git → `https://git-scm.com` → Git for Windows /x64 Setup
- Clone course repository → `git clone https://github.com/MalwareCube/SOC101.git`

### Ubuntu

**Source**

- Ubuntu Desktop → `https://ubuntu.com/download/desktop`