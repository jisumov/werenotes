# Windows Defender Tampering

- Windows Security → Virus & threat protection → Virus & threat protection settings → Manage settings → `Turn Off Tamper Protection`
- Windows PowerShell → Run as administrator
- Disable real-time protection → `Set-MpPreference -DisableRealtimeMonitoring $true`
- Disable network files scanning → `Set-MpPreference -DisableScanningNetworkFiles $true`
- Disable first sight blocking → `Set-MpPreference -DisableBlockAtFirstSeen $true`
- Disable Windows Defender AntiSpyware → `reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f`