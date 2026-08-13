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