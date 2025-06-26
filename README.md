# Dynamic Certificate Generator and Mailer

A Tkinter-based desktop application that lets you batch-generate personalized certificates from a template and spreadsheet, then email them automatically via Gmail SMTP.

---

## Features

- **Upload Certificate Template**: Accepts PNG, JPG, or JPEG images as your base certificate design.
- **Spreadsheet Input**: Reads CSV or Excel (`.csv`, `.xlsx`) files with columns such as `Name`, `Date`, `Event`, `Email`, etc.
- **Field Mapping**: Click on your template preview to map spreadsheet columns to coordinates on the certificate, adjusting font size and color per field.
- **Preview Mode**: See a sample certificate populated with the first row of your data.
- **Batch Generation & Emailing**: Automatically generate all certificates and send each as a PNG attachment to the corresponding email address.
- **Gmail App Password Support**: Securely send mail using a 16-character App Password (no OAuth needed).

---

## Prerequisites

- Python **3.7** or higher
- [pip](https://pip.pypa.io/) installed
- Enable [App Passwords](https://support.google.com/accounts/answer/185833) on your Gmail account (2-Step Verification must be on)

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/<YOUR_USERNAME>/<YOUR_REPO>.git
   cd <YOUR_REPO>
---

### Install dependencies

pip install -r requirements.txt

Contents of requirements.txt:
->pandas
->Pillow

---
## Usage Guide
### 1. Run the App
 -> python certificate_app.py

### 2. Step-by-Step
Step 1: Upload
Click "Upload Certificate Template" and select your PNG/JPG file.

Click "Upload Spreadsheet" and choose your .csv or .xlsx file containing all fields (including an Email column).

Step 2: Map Fields
Adjust Font Size and click "Pick Color" to set a color for your text.

Select a field (e.g. Name, Event) from the dropdown.

Click on the certificate preview to place that field at the desired coordinates.

Repeat for all fields you wish to populate.

Use "Back" or "Next" to navigate.

Step 3: Preview & Generate
Click "Preview" to render a sample certificate using the first row of your spreadsheet.

Click "Generate and Mail All".

In the popup, enter:

Sender Email (your Gmail address)

App Password (16-character key from Google Account)

Email Subject (you can include placeholders like {Name})

Email Body (use {column_name} placeholders, e.g. Hello {Name}, here is your certificate for {Event}.)

Click "Send". The app will generate each certificate, attach it, and send it via SMTP.

Monitor progress in the status label.

Generating a Gmail App Password
Go to your Google Account settings: https://myaccount.google.com/

Navigate to Security on the left menu.

Under "Signing in to Google", enable 2-Step Verification if not already on.

Once 2SV is active, click "App passwords".

Select Mail as the app and Other (Custom name) for the device (e.g., "Cert Generator").

Click Generate and copy the 16-character password.

Use this App Password in the application instead of your main account password.

---

### Troubleshooting
Missing Email Column: Ensure your spreadsheet has a column named Email (case-sensitive).

Font Not Found: If arial.ttf isn’t available on your system, the app will fall back to a default font.

SMTP Errors: Check your App Password and Gmail security settings.

---
