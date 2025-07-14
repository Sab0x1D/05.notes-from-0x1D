# Base64Tool v1.2 — Reverse, Decode & Forensic Analysis

`Base64Tool v1.2` is a lightweight GUI tool designed to help analysts reverse, decode, inspect, and save Base64-encoded content — with an integrated forensics tab for deeper insight into potentially obfuscated or malicious data.

---

## Features

✅ Drag & drop Base64 input  
✅ Reverse Base64 strings before decoding  
✅ Decode Base64 to raw binary or readable text  
✅ Auto-detect file type from decoded output (e.g. EXE, ZIP, PDF)  
✅ Reset / error feedback via status bar  
✅ Built-in **Forensics tab** with detailed triage  

---

## Forensics Tab Overview

After decoding, the **Forensics tab** automatically analyzes the output with 3 key components:

---

### 1. Hex Preview (first 1KB)

Displays the first 1024 bytes of the decoded data in raw hex view:
- Allows visual inspection of headers (e.g. `MZ`, `%PDF`, `504B`)  
- Helps spot embedded shellcode, padding, encryption patterns  
- Useful for quick identification of file structure or content type  

---

### 2. Entropy Score

Calculates **Shannon entropy** of the decoded buffer:
- Helps identify packed or encrypted content  
- High entropy (>7.5) often indicates:
  - Obfuscation
  - Payload encryption
  - Compressed archives

Displayed automatically after decoding:
`Entropy: 7.86 → Possible packed/encrypted content`

---

### 3. Suspicious String Detection

Scans the decoded content for suspicious keywords or patterns using internal regex sets:

- **Malware keywords**: `powershell`, `cmd.exe`, `keylogger`, `rundll32`, `vbscript`  
- **URL/C2 patterns**: `http`, `https`, `discordapp`, IPs with ports  
- **Obfuscation indicators**: `base64`, `gzip`, `xor`, `payload`, `compressed`, `encoded`

All matches are listed below the entropy score to assist fast triage.

---

## File Type Detection

After decoding, the tool auto-identifies file type using **magic byte signatures**:

- `.exe` → `MZ`  
- `.pdf` → `%PDF`  
- `.zip` → `PK`  
- `.png`, `.jpg`, `.gz`, `.rtf`, `.txt`  

The detected type is reflected in:
- The status bar  
- The default extension when saving decoded output

---

## Analyst Use Case

This tool is purpose-built for security analysts needing to:

✅ Triage suspected phishing payloads or obfuscated malware  
✅ Identify embedded binaries or scripts in email attachments  
✅ Decode malware stagers or C2 command blobs  
✅ Quickly assess content for encryption/obfuscation  
✅ Export decoded samples for sandbox or static analysis

---

## Requirements

- Python 3.7+  
- tkinter (preinstalled with Python)  
- `tkinterDnD2` (auto-installed on first run)

---

## How to Use

1. Paste or drag a `.txt` or `.b64` file into the input box  
2. Click **REVERSE** to flip the Base64 string  
3. Click **TRANSFORM** to decode and inspect  
4. Review the **Forensics tab** output  
5. Click **SAVE** to export the decoded file (with correct extension)

---
