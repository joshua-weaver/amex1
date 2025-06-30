# Amex AI Agent

This app automates your monthly Amex reporting process using a Claude-based agent and structured workflows.

## Features
- Searches Gmail and Outlook for your latest Amex statement and receipts
- Applies appropriate accounting codes from an Excel file
- Populates a preformatted Excel cover page
- Assembles a final PDF with cover sheet, statement, and matching receipts

## Setup

### 1. Environment
Install Python 3.9+ and create a virtual environment:
```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
