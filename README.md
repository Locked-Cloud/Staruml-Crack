# StarUML Application Modification Guide

> **⚠️ Educational Purpose Only**  
> This repository is intended strictly for educational purposes to understand application packaging and ASAR file structures. This is not intended to bypass licensing or violate any terms of service.

## Overview

This guide demonstrates how to extract, modify, and repack StarUML application files using ASAR (Atom Shell Archive). Understanding these processes is valuable for developers learning about Electron-based application architecture and file management.

## Prerequisites

Before proceeding, ensure you have the following installed:

- **Node.js** (v14.0 or higher) and **npm**
- **Administrator privileges** on your Windows system
- **StarUML** application installed
- Basic understanding of command-line operations

## Step-by-Step Instructions


### Step 1: Install ASAR Package

ASAR is a simple extensive archive format, similar to tar, that concatenates files into a single package. Install it globally using npm:

```bash
npm install asar -g
```

**Verification:** After installation, verify ASAR is correctly installed by running:
```bash
asar --version
```

### Step 2: Navigate to StarUML Resources Directory

Open **Command Prompt** with **Administrator privileges** (right-click → "Run as administrator") and change directory to the StarUML resources folder:

```bash
cd "C:\Program Files\StarUML\resources"
```

> **Note:** The path may vary depending on your installation directory. Adjust accordingly if StarUML is installed elsewhere.

### Step 3: Extract the ASAR Archive

Create a backup of the original file before proceeding:

```bash
copy app.asar app.asar.backup
```

Extract the contents of `app.asar` into a new `app` folder:

```bash
asar extract app.asar app
```

This command will create an `app` directory containing all the decompressed application files.

### Step 4: Modify Application Files

Navigate to the extracted `app` folder and locate the files you need to modify. In this case, there are **three specific files** that require replacement or modification.

**Important considerations:**
- Maintain the original file structure and naming conventions
- Ensure file permissions remain consistent
- Validate any code changes for syntax errors
- Document all modifications for future reference

### Step 5: Repack the Application

Once modifications are complete, repackage the application into a new ASAR archive:

```bash
asar pack app app.asar
```

This will replace the original `app.asar` file with your modified version.

### Step 6: Restart StarUML

Close StarUML completely (ensure it's not running in the background) and restart the application to load the modified files.

## File Structure

```
C:\Program Files\StarUML\resources\
│
├── app.asar                 # Original packed application
├── app.asar.backup         # Backup copy (created by you)
└── app/                    # Extracted application files
    ├── [various files]
    └── [three target files to modify]
```

## Best Practices

1. **Always create backups** - Keep a copy of `app.asar.backup` before making any changes
2. **Test incrementally** - Make one change at a time and test thoroughly
3. **Document changes** - Keep notes of what files were modified and why
4. **Version control** - Consider using Git to track your modifications
5. **Respect licensing** - Only use this knowledge for legitimate educational purposes


## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| `'asar' is not recognized` | Ensure Node.js and npm are installed and added to PATH. Restart terminal after installation. |
| `Permission denied` errors | Run Command Prompt as Administrator |
| `ENOENT: no such file or directory` | Verify the StarUML installation path is correct |
| StarUML won't start after repacking | Restore from `app.asar.backup` and verify your modifications |
| Files appear corrupted | Ensure original file encoding is preserved during modification |

## Security Considerations

- **Antivirus software** may flag modified executables - add appropriate exceptions if you trust your modifications
- **Code signing** will be invalidated after modification - the application may show unsigned warnings
- **Auto-updates** may overwrite your changes - disable automatic updates if you want to keep modifications

## Educational Value

This guide helps developers understand:

- **ASAR archive format** and its role in Electron applications
- **Application packaging** techniques used in modern desktop applications
- **File system operations** and command-line tooling
- **Software architecture** of Electron-based applications
- **Reverse engineering** concepts for educational analysis

## Legal and Ethical Notice

**IMPORTANT:** This guide is provided solely for educational purposes to help developers understand application packaging and Electron framework architecture.

- ✅ **Permitted:** Learning about ASAR format and Electron application structure
- ✅ **Permitted:** Educational research and experimentation in controlled environments
- ❌ **Not Permitted:** Circumventing software licensing or DRM
- ❌ **Not Permitted:** Distributing modified versions without authorization
- ❌ **Not Permitted:** Commercial use of unlicensed software

**Please purchase a legitimate license** for StarUML if you intend to use it for professional or commercial purposes. Support software developers by respecting their intellectual property.

## Resources

- [ASAR Documentation](https://github.com/electron/asar)
- [Electron Documentation](https://www.electronjs.org/docs)
- [StarUML Official Website](https://staruml.io/)
- [Node.js Official Website](https://nodejs.org/)

## Contributing

Contributions to improve this educational guide are welcome. Please ensure all contributions maintain the educational focus and ethical standards outlined above.

## Disclaimer

**This repository is for educational purposes only.** The authors and contributors:

- Do not encourage or condone software piracy or license violation
- Are not responsible for any misuse of this information
- Recommend purchasing legitimate licenses for all commercial software
- Provide this information to aid in understanding software architecture and packaging

**Use at your own risk.** Modifying application files may:
- Void your software warranty
- Violate terms of service agreements  
- Cause application instability or data loss
- Trigger security software alerts

Always backup your data and system before making modifications.

## License

This educational guide is released under the MIT License. See LICENSE file for details.

---

**Remember:** Knowledge is power, but with power comes responsibility. Use this information ethically and legally.