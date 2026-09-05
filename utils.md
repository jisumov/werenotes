# WSL Installation

- Open Terminal
- Install WSL → `wsl --install`
- Enable Virtual Machine → `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
- Turn Windows features on or off
- Enable `Windows Subsystem for Linux`

# SSH Key Setup

- Open Terminal
- Create SSH Key → `ssh-keygen -t ed25519 -C "<EMAIL>"`
- Create passphrase
- Initialize SSH agent → `eval "$(ssh-agent -s)"`
- Add key to the SSH agent → `ssh-add ~/.ssh/id_ed25519`
- Show SSH key → `cat ~/.ssh/id_ed25519.pub`
- Open GitHub
- Settings → Access → SSH and GPG keys → New SSH key
- Paste all the SSH key

# Repository Configuration

- Add repository → `git remote add origin <GIT_URL>`
- Verify references → `git remote -v`
- Configure username → `git config --global user.name "<USERNAME>"`
- Configure email → `git config --global user.email "<EMAIL>"`

# Windows Defender Tampering

- Windows Security → Virus & threat protection → Virus & threat protection settings → Manage settings → `Turn Off Tamper Protection`
- Open PowerShell → Run as administrator
- Disable real-time protection → `Set-MpPreference -DisableRealtimeMonitoring $true`
- Disable network files scanning → `Set-MpPreference -DisableScanningNetworkFiles $true`
- Disable first sight blocking → `Set-MpPreference -DisableBlockAtFirstSeen $true`
- Disable Windows Defender AntiSpyware → `reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f`