# GST RECO — Enterprise Desktop Reconciliation Platform

[![Latest Release](https://img.shields.io/badge/latest%20release-v1.2.4-teal.svg)](https://github.com/sdrkstar/support_reco/releases/latest)
[![License: MIT](https://img.shields.io/badge/License-MIT-emerald.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20x64-blue.svg)](https://github.com/sdrkstar/support_reco/releases/latest)

**GST RECO** is a high-performance offline Windows desktop application built for Chartered Accountants, Tax Professionals, and Finance Teams to reconcile GST Purchase Registers, Sales Registers, GSTR-2B, GSTR-3B, and Electronic Ledgers with high speed and zero data leakage.

---

## 🌟 Key Features

- ⚡ **Multi-Module Reconciliation Engine**:
  - **GSTR-2B vs Books**: Matched, Unmatched 2B, Unmatched Books, and Side-by-Side Bill Differences.
  - **GSTR-3B vs Books**: ITC comparison and tax liability variance calculation.
  - **GST Ledger Detailed Report**: Cash vs Credit ledger reconciliation.
  - **Sales vs 3B & Output Sheet**: Outward supply tax verification.
  - **Quick Reco**: One-click instant multi-file reconciliation.
- 📊 **Formula-Linked Excel Exporters**: Generates `.xlsx` workbooks with live Excel formulas, zero control-character artifacts (`_x000D_`), and custom styled borders.
- 🖨️ **Landscape Print & PDF Engine**: Pixel-perfect printable reports with auto-scaling table headers and expanded party bill line items.
- 🔄 **In-App Auto-Update System**: Integrated version detection, progress-bar installer downloader, and one-click app relaunch engine.
- 🔒 **100% Offline & Private**: Embedded FastAPI backend + local SQLite database ensures client financial data never leaves your computer.

---

## 🚀 Installation

### Downloading Pre-Built Installers

1. Go to the [Latest Releases](https://github.com/sdrkstar/support_reco/releases/latest) page on GitHub.
2. Download the installer executable matching the latest release (e.g., `Reco Setup v*.exe`).
3. Run the installer to set up GST RECO on your Windows machine.

---

## 🛠️ Development & Building from Source

### Prerequisites
- **Node.js**: v18.0.0 or higher
- **Python**: v3.10 to v3.14
- **PyInstaller**: `pip install pyinstaller`

### 1. Clone & Install Dependencies
```bash
git clone https://github.com/sdrkstar/support_reco.git
cd support_reco
npm install
pip install -r backend/requirements.txt
```

### 2. Run Locally in Development Mode
```bash
npm run dev
```

### 3. Automated One-Click Production Build
Run the automated PowerShell build script from the project root:
```powershell
.\build-release.ps1
```
This script will:
1. Compile the React/Vite frontend into `dist/`.
2. Bundle the FastAPI Python backend into a single executable `backend/dist/backend.exe` using PyInstaller.
3. Package the complete Electron desktop app and NSIS setup installer into `dist/`.

The compiled setup installer will be generated at:
```
dist/Reco Setup v<version>.exe
```
*(where `<version>` is automatically read from `package.json`)*.

---

## 🏗️ Architecture Overview

GST RECO operates as an isolated, high-performance desktop application:

- **Frontend**: Electron (main process) + React + Vite + TailwindCSS.
- **Backend Engine**: Embedded Python FastAPI process compiled with PyInstaller, listening on a dynamic localhost port.
- **IPC Layer**: Context-isolated Electron IPC bridge connecting renderer UI components directly to local backend API routes.
- **Persistence**: Local SQLite database and temporary OS file storage with zero external cloud dependencies.

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
