# Adobe Creative Cloud Full Uninstall Script

This script fully automates the **silent removal of Adobe Creative Cloud applications** on **Apple Silicon Macs running macOS Sonoma**.  
It includes:

- ✅ Per-app detection and removal (Photoshop, Illustrator, etc.)
- ✅ Silent uninstallation of Creative Cloud Desktop
- ✅ Execution of the Adobe Cleaner Tool
- ✅ Residual file cleanup
- ✅ Timestamped logging of all actions
- ✅ Color-coded terminal output for clarity

---

## 🚀 How to Run the Script

1. **Transfer the script to your Mac** and open the **Terminal**.

2. **Make the script executable**:
   ```bash
   chmod +x /path/to/adobe-uninstall.sh
   ```

3. **Run the script with superuser privileges**:
   ```bash
   sudo /path/to/adobe-uninstall.sh
   ```

54 **View the log file** after execution:
   ```bash
   cat /var/log/adobe-uninstall-YYYY-MM-DD-HH-MM.log
   ```

Each run creates a unique, timestamped log file located at:
```
/var/log/adobe-uninstall-[DATE]-[TIME].log
```

---

## ⚠️ Potential Issues & Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| **TCC Permission Denied** | macOS privacy controls block full disk access | Pre-approve Full Disk Access via MDM (Jamf, Mosyle) or manually grant Terminal Full Disk Access in **System Settings → Privacy & Security → Full Disk Access** |
| **App Not Found Warnings** | Some Adobe apps may not be installed on all machines | These are informational and harmless; the script skips missing apps |
| **Cleaner Tool Fails to Download** | No internet connection or Adobe URL changed | Verify internet access and update the script with the latest URL from Adobe's website if necessary |
| **Uninstaller Not Found** | CC Uninstaller is missing | Ensure the Creative Cloud Desktop app is installed, or skip this step if it has already been removed |

---

## ✅ Requirements
- macOS **Sonoma**
- Apple Silicon (**arm64** architecture)
- **sudo** or root privileges
- Internet connection (for downloading Adobe Cleaner Tool)

---

## 💡 Notes
- For complete deletion of some user-level files, the script may require **Full Disk Access** due to macOS privacy restrictions (TCC).
- For large-scale deployment, consider pairing this script with MDM policies to handle permissions automatically.

---

## 📝 License
This script is provided **as-is** without warranty. Use at your own risk.
