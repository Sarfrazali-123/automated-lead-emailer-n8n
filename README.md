# 📧 Automated Lead Outreach Workflow using n8n, Google Sheets & Gmail

This repository contains an **n8n workflow** designed to automate lead outreach by integrating **Google Sheets**, **Gmail**, and custom logic for personalization and logging.

---

## 🖼️ Demo Workflow Preview

![Workflow Demo](https://github.com/Sarfrazali-123/automated-lead-emailer-n8n/blob/c53f183b08d23e12c8bb7814247c86ea685e13f7/cold%20-email.PNG)  
<!-- Replace demo.png with your actual image file name -->

---

## 🚀 Overview

This workflow automates the process of sending personalized emails to leads stored in Google Sheets.  
It ensures each lead is contacted only once, selects a random email template, personalizes the message, sends it via Gmail, and logs the status back into the sheet.

---

## ✅ Features

- Fetch leads from Google Sheets  
- Skip leads that already have `Send Status = SENT`  
- Select a random email template from a second sheet  
- Dynamic personalization (replaces `[name]` automatically)  
- Send automated emails using Gmail  
- Log status + timestamp back into Google Sheets  
- Batch processing & wait logic to avoid API limits  
- Custom JavaScript for template processing  

---

## 🧩 Workflow Structure

1. **Manual Trigger** – Start the workflow manually.  
2. **Get Leads** from Google Sheets.  
3. **If Condition** filters out already contacted leads.  
4. **Loop Through Items** with batching.  
5. **Get Email Templates** from another sheet.  
6. **Code Node** selects a random template and converts it to HTML.  
7. **Merge Nodes** combine template + lead data.  
8. **Edit Fields** personalizes the email body.  
9. **Gmail Node** sends the email.  
10. **Logging** updates send status & timestamp in Google Sheets.  
11. **Wait Node** adds delay between each batch.  

## 📦 Requirements

To run this workflow, you need:

- An **n8n instance** (Cloud or Self-hosted)  
- A **Google Sheets OAuth credential**  
- A **Gmail OAuth credential**  
- A Google Sheets Lead Sheet with columns:
  - `Name`
  - `Email`
  - `Send Status`
  - `Time`
- A Template Sheet with:
  - `Subject`
  - `Body`
