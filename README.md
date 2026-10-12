# Tista & Dropbox Bulk Order Downloader

Windows desktop application for downloading and processing bulk Tista orders with Dropbox integration.

## Features

- **Tista Card & Dropbox Integration**:
  - Accepts Tista Order URLs (e.g. `https://tista.app/order/5291401183317/#454758`) or Order IDs (e.g. `#454758`).
  - Automatically identifies customer original files via the **Open files in Dropbox** button (`\order\5291401183317\#454758`).
  - Identifies vendor completed deliveries via **Completed links** (e.g. `https://www.dropbox.com/t/...`).
  - **Open Dropbox** button on each card to view folders in the web browser with one click.
- **Dropbox Folder & Size Analysis**:
  - Resolves the Dropbox `--` display to calculate real folder file count and sizes (MB/GB).
- **Flexible File Selection**:
  - **Own Selection (Top 5 Samples)**: Downloads top 5 sample images for rapid QC inspection without waiting for 20–23 GB archives.
  - **Select All**: Downloads full order archive.
- **Smart Queue & Skip Logic**:
  - Individual **Download Order** button for selective processing.
  - Master **Download All Queued Orders** button with real-time progress bar.
  - Automatically skips orders already running or completed so existing jobs are not interrupted or duplicated.
- **Automated Extraction & Verification**:
  - Automatically extracts `.zip` archives into `{Save Location}/{Date}/{Vendor}/#{OrderID}/Completed/`.
  - Verifies file count and integrity.
  - Safely deletes temporary `.zip` files upon 100% verification.

## How to Run

### Method 1: Standalone Executable (Recommended)
Double-click `OrderDownloader.exe` in the root folder. No Python installation needed.

### Method 2: Batch Launcher
Double-click `run_app.bat`.

### Method 3: Python Environment
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

## Compilation to .EXE
```bash
pyinstaller --noconsole --onefile --collect-all customtkinter --name OrderDownloader main.py
```
