# IT3040 Assignment 1 – Playwright Automation Test

## Overview

This project automates one test scenario for the website [https://www.pixelssuite.com/](https://www.pixelssuite.com/) as part of IT3040 (ITPM) Assignment 1.

**Feature Tested:** Image Format Conversion (Convert to PNG)  
**Test Scenario:** Verify that a valid PNG image file uploaded to the Image Format Conversion tool is correctly displayed in the Preview section. 
**Test Type:** Positive  
**Tool Used:** Playwright (Python)

---

## Prerequisites

- Python 3.11 or Python 3.12 installed ([https://www.python.org/downloads/](https://www.python.org/downloads/))
  - During installation, check **"Add Python to PATH"**
- Google Chrome installed (recommended) — or Playwright will install Chromium automatically

---

## Project Structure

```
test_automation_ui/
├── image_preview_test.py   # Main Playwright test script
├── execution_results.csv   # Auto-generated test execution results
├── sample.png              # Sample PNG image used for testing
├── results/                # Folder where screenshots are saved
└── README.md               # This file
```

---

## Setup Instructions (One-Time)

1. Save this project folder to your **D: drive** so the path is:  
   `D:\test_automation_ui`

2. Open **Command Prompt** and navigate to the folder:
   ```
   cd /d D:\test_automation_ui
   ```

3. Install the required Python packages:
   ```
   pip install -U pip
   pip install playwright openpyxl
   playwright install
   ```

---

## Running the Test

From the `D:\test_automation_ui` directory in Command Prompt, run:

```
python image_preview_test.py --url "https://www.pixelssuite.com/convert-to-png" --slow-mo-ms 2000
```

A browser window will open automatically. The script will:
1. Navigate to the Image Format Conversion page
2. Upload the `sample.png` file
3. Check whether a preview of the image is displayed
4. Save a screenshot to the `results/` folder
5. Append one row of results to `execution_results.csv`

---

## Checking Results

After running the script:

- Open `execution_results.csv` — it should contain **one data row** (plus the header) with columns:
  - `file_type` — PNG
  - `file_path` — full path to the sample PNG
  - `preview_detected` — TRUE or FALSE
  - `status` — PASS or FAIL
  - `screenshot` — path to the saved screenshot

- Open the `results/` folder — it should contain a file named `preview_pass.png` (screenshot taken when the preview was detected).

---

## Test Case Details

| Field | Value |
|---|---|
| TC ID | Pos_0010 |
| Feature | Image format conversion |
| Input | Upload a valid PNG image to the Convert to PNG tool |
| Expected Output | The uploaded PNG image should be displayed in the Preview section |
| Tool | Playwright (Python, Chromium) |
| Script | image_preview_test.py |
#
