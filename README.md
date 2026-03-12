# Azure-Web-Services-Deployment
# Learn how to host a website on Azure's enterprise cloud infrastructure.
This repository provides a complete, step-by-step guide for deploying a static website (HTML, CSS, and JS) to Azure App Service using the Kudu File Manager.

# Azure-Web-Services-Deployment
# Learn how to host a website on Azure's enterprise cloud infrastructure.
This repository provides a complete, step-by-step guide for deploying a static website (HTML, CSS, and JS) to Azure App Service using the Kudu File Manager.

## Overview
This document describes the complete process of deploying a ready-made single HTML file website to Microsoft Azure App Service using the Azure Portal and Kudu File Manager. No CLI or code required.

## Tools Used
* Microsoft Azure Portal (portal.azure.com)
* Azure App Service — Linux, Free F1 Tier
* Kudu File Manager (built-in deployment tool)
* A single `index.html` file (zipped)

## Prerequisites
* An active Microsoft Azure account
* Your website file (`index.html`) ready on your computer
* The file zipped into a `.zip` archive

---

## Deployment Steps

### Step 1 — Zip Your File
Before deploying, your HTML file must be zipped:
* Right-click your `index.html` file
* Select "Send to" → "Compressed (zipped) folder" on Windows
* Make sure `index.html` is at the ROOT of the ZIP, not inside a subfolder

### Step 2 — Create a Web App on Azure Portal
* **Step 1: Go to Azure Portal**
  Visit portal.azure.com and log in to your account.
* **Step 2: Create a Resource**
  Click "Create a resource" → search for "Web App" → click Create.
* **Step 3: Fill in the App Details**
  Fill in the form with these settings:

| Field | Value |
| :--- | :--- |
| Resource Group | Create new → e.g. my-site-rg |
| Name | e.g. mylinuxsite123 (this becomes your URL) |
| Publish | Code |
| Runtime Stack | PHP 8.2 |
| Operating System | Linux |
| Region | Central India (or closest to you) |
| Pricing Plan | Free F1 — Dev/Test |

* **Step 4: Review and Create**
  Click "Review + Create" → then "Create". Wait approximately 2 minutes for Azure to provision the resource.
* **Step 5: Go to Resource**
  Once complete, click "Go to resource" to open your Web App.

### Step 3 — Open Kudu File Manager
* **Step 1: Find the Kudu URL**
  In your browser, the Azure Portal. Look for development tools > advance tools > go ➡️ > KUDU webpage open.
* **Step 2: Navigate to File Manager**
  Navigate to File Site.
* **Step 3: Open the wwwroot folder**

### Step 4 — Upload Your ZIP File
* **Step 1: Drag and Drop**
  At the bottom of the File Manager page you will see: "Drag a Zip File here to extract & upload, or click to select one".
* **Step 2: Drop your ZIP**
  Drag your zipped `index.html` file onto that area. Azure will automatically extract it into the `wwwroot` folder.
* **Step 3: Verify**
  You should now see your `index.html` listed in the `wwwroot` directory.

### Step 5 — Visit Your Live Website
* **Step 1: Copy your Default Domain**
  Go back to Azure Portal → Your Web App → Overview. Find "Default domain" on the right side.
* **Step 2: Open in Browser**
  Your live URL will be
* **Step 3: Done!**
  Your website is now live and accessible to anyone on the internet.

---

## Important Notes
* The Free F1 plan has limited resources but is perfect for demos and internship tasks.
* If the site shows a default Azure page, wait 1-2 minutes and refresh — the container may still be starting.
* Make sure `index.html` is at the root of the ZIP file, not inside a subfolder, otherwise the site will not load.
* PHP 8.2 runtime is used because it natively serves static HTML files on Linux without any extra configuration.
* The Kudu File Manager URL uses `.scm.` in the domain — this is the deployment/management endpoint.

## Quick Reference Summary
The complete deployment process in 5 simple steps:

| # | Action | Where |
| :--- | :--- | :--- |
| 1 | Zip your file | Your local computer |
| 2 | Create Web App | portal.azure.com → Create Resource |
| 3 | Open Kudu File Manager | yourapp.scm.azurewebsites.net/fileManager |
| 4 | Navigate to site/wwwroot | Kudu File Manager |
| 5 | Drag & drop ZIP | Bottom of File Manager page |
