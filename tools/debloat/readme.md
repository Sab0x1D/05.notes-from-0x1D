# Windows 10/11 Debloater

This GUI-based tool provides analysts, malware researchers, and power users with a streamlined way to harden and debloat Windows 10/11 systems — particularly useful for setting up clean virtual machines or testbeds during malware lab preparation.

Designed with verbose output, elevation enforcement, and selectable task execution, this utility ensures clarity and control over Windows service and bloatware removal operations.

> See how this integrates into a full analysis lab setup: 
> [mal_lab_setup](https://github.com/Sab0x1D/mal_lab_setup)

---

## Features

✅ **Runs with admin elevation** (auto-relaunches if needed)  
✅ **Live PowerShell execution log** in the app window  
✅ **Parallel tasking with threading support**  
✅ **All actions optional & selectable by checkbox**

---

## Available Actions

Each toggle corresponds to a real PowerShell execution block with live feedback:

- **Remove Bloatware**  
  Uninstalls a curated list of Microsoft Store apps

- **Disable Telemetry**  
  Stops & disables `DiagTrack`, adjusts registry for max privacy

- **Disable Cortana**  
  Removes Cortana via registry policy enforcement

- **Disable Unused Services**  
  Shuts down and disables Fax, RemoteRegistry, XblGameSave, RetailDemo

- **Enable High Performance Power Plan**  
  Forces activation of `SCHEME_MIN` (Ultimate Performance)

- **Remove OneDrive**  
  Kills OneDrive process and runs uninstaller (SysWOW64 or fallback)

- **Disable Windows Defender**  
  Turns off real-time protection, script scanning, IOAV, etc.

- **Block Windows Updates**  
  Stops `wuauserv`, disables service and sets NoAutoUpdate registry key

---

## How To Use

1. Double-click  
2. Allow elevation prompt (required for registry/service modifications)  
3. Tick the actions you want to apply  
4. Click **"Apply Selected Actions"**  
5. Review PowerShell logs in the integrated window  

---

## Who Is This For?

This tool is built for:

- Cybersecurity professionals preparing malware analysis VMs
- Researchers creating clean, controlled test environments
- Advanced users looking to disable noise and harden Windows systems

This can be used as part of your **malware lab setup** or for **baseline provisioning** of security research virtual machines.

---

## Notes

- All PowerShell scripts are executed with `-ExecutionPolicy Bypass`  
- Registry paths are created if not already present  
- No reboot is performed automatically — reboot manually afterward if needed

---

## Related Repos

- 💻 [mal_lab_setup](https://github.com/Sab0x1D/mal_lab_setup) — Full gateway + Windows analysis VM configuration
