# MadHat - Operative Fundamentals

## The Silicon Brain (Processes & Persistence)

### Understanding the Machine

- Von Neumann Architecture → CPU and RAM

**The CPU (The Chef)**

- Central Processing Unit → Takes instructions → Executes them
    - Clock Speed (GHz) → How fast
    - Cores → How many hands

**The RAM (The Countertop)**

- Random Access Memory → CPU puts data and code → Real-time usage
    - Small (16GB - 32GB) and instant (nanoseconds)

**Storage**

- RAM is cleaned when powered off → Urgent data preservation
- SSD → Solid State Drive → Fast (microseconds)
- HDD → Hard Disk Drive → Spinning physical disks (milliseconds)

**RAM, SSD and HDD Differences**

- Throughput (Bandwidth)
    - RAM → 50 GB/s
    - SSD → 550 MB/s - 14 GB/s
    - HDD → 160 MB/s
- Latency (Response Time)
    - RAM → 14 nanoseconds
    - SSD → 100K - 30K nanoseconds
    - HDD → 15M nanoseconds

**The Bottleneck**

- High CPU & Low RAM → Swapping → Back and forth memory management
- Low CPU & High RAM → Processing Imbalance

**Processes vs. Services**

- Process → Specific job → Use CPU and RAM
    - Foreground Processes → Visible Apps
    - Background Processes & Services → Noise
    - Parent Process → Omnipotent creator
    - Child Process → The creation
- Services → Run often with SYSTEM privileges

**Why Cybersecurity Operators Care**

- Resource Exhaustion → Process takes up all the RAM
- The Hang → Process awating a non-existent response

**Process Tree**

- Hierarchical structure → Maps parent-child relationships
    - Normal → Open Word (winword.exe) → Type a document
    - Abnormal → Open Word (winword.exe) → Command Prompt spawns (cmd.exe)

### Task Manager

**Beyond the Theory**

- Operative View → Details tab

**The PID (Process ID)**

- PID → Unique identifier
    - Reboot or Crash → New PID
    - PID changes → Sign of instability or persistence fighting
        - Parent Process (PPID) might fail to keep the child alive
        - Malware mechanism → Difficult to terminate

**The "Command Line" Column**

- Task Manager → Details tab → Right click the top header bar → Enable "Command Line"

    - Safe → `C:\Windows\System32\svchost.exe -k netsvcs`
    - Malicious → `C:\Temp\svchost.exe`

**The "Path" Loophole**

- Programs with the same name → Can run from different folders

**Hiding in Plain Sight**

- Filename → That looks similar
    - Typos → `cvchost.exe` instead of `svchost.exe`
    - Unicode → Same characters from different "alphabets"
- Path → Legitimate filename → Bad folder
    - Malicious → `notepad.exe` → Running from Downloads
    - Detection → Via "Command Line" or "Path" columns
- Resource Hiding → 0% CPU usage → Do not show up

**Performance Tab**

- Spikes → Anomalies in resource consumption
    - Cryptojackers → Mine cryptocurrency → High CPU or GPU usage
    - High "Up time" → Machine has not rebooted → Security patches not applied

**App History Tab**

- Historical applications executions
    - Useful against malware that lives for short period of time
    - `Uninstalled processes` → High network usage → Living Off the Land (LOLBins) 

**Network Usage vs. CPU Time**

- Identify anomalies → Sort by Network → `notepad.exe` has network data → Data exfiltration point

**Startup Apps**

- Malware's goal → Achieve persistence
    - Check → "Startup impact" & "Publisher"
    - Suspicious → Enabled "Status" & Blank "Publisher"

**Users Tab**

- Generally only shows own username
    - Windows 11 → One user session at a time
    - Windows Server → Multiple RDP sessions
    - Malicious → Unfamiliar account → RDP or RAT → via `cmd.exe` or `powershell.exe`

**Services Tab**

- Run in the background → Favorite for APTs
    - Malicious → Mimic legitimate services → W32Time (legit) vs. W32Times (fake)
    - Verify legitimacy → Right click the service → Hit "Search online"