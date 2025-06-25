# ProviderOne Batch Billing Automation

**An internship project to automate the batch billing process for Washington State's ProviderOne portal.**  
Supports services like **Respite** and **Specialized Habilitation**, used by DSHS providers.

---

## Overview

This tool automates the intake and formatting of billing data for submission to the ProviderOne system. It supports two versions:

- **Version 1: HTML + JavaScript (no backend)**  
  Converts Excel spreadsheets into formatted CSV files for manual upload.
  
- **Version 2: Node.js + Puppeteer Backend**  
  Automates the entire billing flow — from Excel parsing to online claim form submission.

---

## Features

| Feature                               | HTML/JS Version | Node.js/Puppeteer Version |
|--------------------------------------|------------------|----------------------------|
| Upload Excel (.xlsx) file            | ✅               | ✅                         |
| Format data to ProviderOne structure | ✅               | ✅                         |
| Download as CSV                      | ✅               | ❌                         |
| Automatically log in and submit      | ❌               | ✅                         |
| Runs in browser only                 | ✅               | ❌                         |

---

## 🖥 Version 1: Frontend-Only (HTML + JS)

### Tech Used
- HTML5 + JavaScript
- [`xlsx.js`](https://github.com/SheetJS/sheetjs) for Excel parsing


### How to Run
1. Open `index.html` in your browser.
2. Upload your Excel file.
3. View the formatted data and download the `.csv`.

### Input Format (Excel Columns)
- ProviderID
- ClientID
- Authorization#
- ServiceDateFrom
- ServiceDateTo
- ServiceCode
- Modifiers (comma-separated if multiple)
- Units

### Output
CSV file ready for upload to the ProviderOne batch submission portal.

---

## 🖥 Version 2: Fullstack (Node.js + Puppeteer)

### Tech Used
- Node.js + Express
- Puppeteer (browser automation)
- Multer (file upload)
- dotenv
- xlsx


### Setup

```bash
git clone <repo_url>
cd providerone-batch
npm install

### How to Run
node server.js
open: http://localhost:3000
Upload your Excel billing file, and the tool will:
- Log in to ProviderOne
- Fill each service line
- Submit the batch
