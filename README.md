### 🛡️ REMnux: Getting Started

**Room:** [REMnux: Getting Started — TryHackMe](https://tryhackme.com/room/remnuxgettingstarted)  
**Status:** ✅ Completed  
**Date:** *13 June 2025*

---

### 🎯 Objective  
This room introduced the **REMnux VM**, a specialised Linux distro packed with malware analysis tools. The goal was to explore basic file analysis with `oledump.py`, simulate malware activity with `INetSim`, and get hands-on with memory forensics using `Volatility 3` and `strings`.

---

### 🗝️ Key Concepts  
- **REMnux VM** — A Linux distro tailored for malware analysis with tools like Volatility, YARA, oledump, and INetSim.  
- **oledump.py** — Used to analyse OLE2 (Office-style) documents and extract embedded macros.  
- **PowerShell Obfuscation** — Common tactic in malware to hide malicious script logic.  
- **INetSim** — A fake network simulation tool for analysing malware that tries to "phone home" or download files.  
- **Volatility 3** — A memory forensics framework used to analyse memory dumps.  
- **strings (Linux command)** — Used to extract readable text from binary files, helpful in early triage and analysis.

---

### 🛠️ Tools Used  
- **oledump.py** — Used to identify and decompress embedded VBA macros in `.xlsm` files.  
- **CyberChef** — Used to de-obfuscate and clean PowerShell commands for analysis.  
- **INetSim** — Simulated a fake internet environment to capture network activity from malware.  
- **Volatility 3** — Ran multiple plugins on a memory image to extract processes, DLLs, command lines, and more.  
- **strings** — Pulled ASCII and Unicode strings from memory for further inspection.

---

### ⚠️ Challenges Faced  
- The VBA macro was heavily obfuscated, making the PowerShell script hard to read at first.  
- The raw Volatility output was overwhelming, especially when not saved properly.  
- Fixed this by using `CyberChef` for de-obfuscation and looping Volatility plugins into text files for clean review.

---

### 🧠 What I Learned  
- How to use `oledump.py` to inspect and extract macros from suspicious Office files.  
- How attackers use simple PowerShell tricks like `*` and `^` to evade detection.  
- How INetSim mimics a real network to safely monitor malware’s C2 activity or downloads.  
- How to preprocess memory images using Volatility 3 plugins and batch save outputs.  
- How `strings` can quickly pull out readable content (even Unicode) for fast analysis.

---

### 🌐 Real-World Application:  
> Analysts often need to reverse engineer suspicious files in a safe, contained environment.  
> REMnux provides this out-of-the-box, allowing quick triage, network observation, and memory forensics without compromising your real machine. Perfect for malware analysts, incident responders, and forensic teams.

---

### 💭 Reflections:  
- I really enjoyed the hands-on approach — seeing the macro download and run a binary was eye-opening.  
- INetSim was especially cool; it gave me ideas on building a test environment.  
