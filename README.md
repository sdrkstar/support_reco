# GST RECO — Enterprise Desktop Reconciliation Platform

[![Version](https://img.shields.io/badge/version-1.2.2-teal.svg)](https://github.com/sdrkstar/gst_reco/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-emerald.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20x64-blue.svg)](https://github.com/sdrkstar/gst_reco/releases)

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

1. Go to the [Releases](https://github.com/sdrkstar/gst_reco/releases) page.
2. Download the latest installer: **`Reco Setup v1.2.2.exe`**.
3. Run the installer to install GST RECO on Windows.

---

## 🛠️ Development & Building from Source

### Prerequisites
- **Node.js**: v18.0.0 or higher
- **Python**: v3.10 to v3.14
- **PyInstaller**: `pip install pyinstaller`

### 1. Clone & Install Dependencies
```bash
git clone https://github.com/sdrkstar/gst_reco.git
cd gst_reco
npm install
pip install -r backend/requirements.txt
```

### 2. Run Locally in Development Mode
```bash
npm run dev
```

### 3. Build Backend Binary (`backend.exe`)
```bash
pyinstaller backend.spec --noconfirm
powershell -Command "Copy-Item -Path 'dist/backend.exe' -Destination 'backend/dist/backend.exe' -Force"
```

### 4. Package Windows Production Installer
```bash
npm run build
npm run package:app
```
The compiled setup installer will be generated in `dist-v122/Reco Setup v1.2.2.exe`.

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
