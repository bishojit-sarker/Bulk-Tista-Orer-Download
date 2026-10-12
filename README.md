# Tista Bulk Order Downloader

Windows desktop application for downloading bulk Tista orders directly from Dropbox button folders.

## Features

- **Tista Card & Dropbox Integration**:
  - Accepts Tista Order URLs (e.g. `https://tista.app/order/5291401183317/#454758`), Server paths (`\order\5291401183317\#454758`), or Order IDs (`#454758`).
  - **Exclusively uses Dropbox Button**: Completely ignores extraneous Completed Transfer links, entering directly through the **Open files in Dropbox** button.
  - **Open in Dropbox Button**: Each card has a dedicated button to open the Dropbox order folder in your default browser.
- **Folder Breakdown & Left Responsive Checkboxes**:
  - Scans all subfolders inside the Dropbox button location (e.g., `clipping_pix`, `pixel_path`, `Original`, etc.).
  - Resolves Dropbox `--` display to show accurate file count and size (MB/GB).
  - **Left-aligned responsive checkboxes** for each folder so you can tick only the folders you want to download.
- **Own Selection Modal Window**:
  - Click **Own Selection...** on any folder to open a checklist dialog.
  - Select individual files, or use the **Top 5 QC (Fast)** quick button for rapid quality checks without downloading 20–23 GB archives.
- **Default Save Location**:
  - Defaults to `E:\Audit` (with hierarchical subfolders `{Month}\{Week}\{Vendor}\#{OrderID}\`).
- **Smart Queue & Skip Logic**:
  - Individual **Download Order** button for selective processing.
  - Master **Download All Queued Orders** button with a real-time progress bar.
  - Automatically skips orders already running or completed.
- **Automated Extraction & Verification**:
  - Automatically unzips downloaded archives into `E:\Audit\{Month}\{Week}\{Vendor}\#{OrderID}\`.
  - Verifies file integrity and count.
  - Safely deletes temporary `.zip` files upon 100% verification.

## How to Run

### Method 1: Standalone Executable (Recommended)
Double-click `OrderDownloader.exe` in the root folder. No Python installation needed.

### Method 2: Batch Launcher
Double-click `run_app.bat`.

### Method 3: Python Virtual Environment
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python main.py
```
