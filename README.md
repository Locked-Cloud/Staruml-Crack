# StarUML Modification Guide

> **⚠️ For Educational Purposes Only**

This guide demonstrates how to modify StarUML application files by extracting, editing, and repacking the ASAR archive.

## Prerequisites

- Node.js and npm installed
- Administrator access
- StarUML installed

## Modification Process

### 1. Install ASAR

```bash
npm install asar -g
```

### 2. Navigate to StarUML Resources

Open **Command Prompt as Administrator**:

```bash
cd "C:\Program Files\StarUML\resources"
```

### 3. Backup Original File

```bash
copy app.asar app.asar.backup
```

### 4. Extract ASAR Archive

```bash
asar extract app.asar app
```

### 5. Modify Files

Replace these three files in the `app` folder with the modified versions from this repository:

- `app/src/engine/license-store.js`
- `app/src/dialogs/license-activation-dialog.js`
- `app/src/engine/diagram-export.js`

### 6. Repack the Application

```bash
asar pack app app.asar
```

### 7. Restart StarUML

Close and restart StarUML to apply changes.

## Quick Command Reference

```bash
# Complete process
npm install asar -g
cd "C:\Program Files\StarUML\resources"
copy app.asar app.asar.backup
asar extract app.asar app
# Replace the three files manually
asar pack app app.asar
```

## Troubleshooting

| Issue                      | Solution                                      |
| -------------------------- | --------------------------------------------- |
| `'asar' is not recognized` | Restart terminal after installing npm package |
| Permission denied          | Run Command Prompt as Administrator           |
| StarUML won't start        | Restore from `app.asar.backup`                |

## Important Notes

- **Backup first** - Always keep `app.asar.backup`
- **Administrator required** - Must run CMD as admin
- **For learning only** - Educational purposes to understand Electron apps

## Disclaimer

This is for educational purposes only. Purchase a legitimate StarUML license for commercial use. Modifying application files may violate terms of service.

---

**Educational purposes only. Support developers by purchasing legitimate software licenses.**
