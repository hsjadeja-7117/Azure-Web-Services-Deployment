# Azure-Web-Services-Deployment
# Learn how to host a website on Azure's enterprise cloud infrastructure.
This repository provides a complete, step-by-step guide for deploying a static website (HTML, CSS, and JS) to Azure App Service using the Kudu File Manager.

# [cite_start]Deploying a Website to Azure App Service [cite: 1]

> Learn how to host a website on Azure's enterprise cloud infrastructure. This repository provides a complete, step-by-step guide for deploying a static website (HTML, CSS, and JS) to Azure App Service using the Kudu File Manager.

## [cite_start]Overview [cite: 4]
[cite_start]This document describes the complete process of deploying a ready-made single HTML file website to Microsoft Azure App Service using the Azure Portal and Kudu File Manager[cite: 5]. [cite_start]No CLI or code required[cite: 6].

## [cite_start]Tools Used [cite: 7]
* [cite_start]Microsoft Azure Portal (portal.azure.com) [cite: 8]
* [cite_start]Azure App Service — Linux, Free F1 Tier [cite: 9]
* [cite_start]Kudu File Manager (built-in deployment tool) [cite: 10]
* [cite_start]A single `index.html` file (zipped) [cite: 11]

## [cite_start]Prerequisites [cite: 12]
* [cite_start]An active Microsoft Azure account [cite: 13]
* [cite_start]Your website file (`index.html`) ready on your computer [cite: 14]
* [cite_start]The file zipped into a `.zip` archive [cite: 15]

---

## [cite_start]Deployment Steps [cite: 16]

### [cite_start]Step 1 — Zip Your File [cite: 17]
[cite_start]Before deploying, your HTML file must be zipped[cite: 18]:
* [cite_start]Right-click your `index.html` file [cite: 19]
* [cite_start]Select "Send to" → "Compressed (zipped) folder" on Windows [cite: 20]
* [cite_start]Make sure `index.html` is at the ROOT of the ZIP, not inside a subfolder [cite: 21]

### [cite_start]Step 2 — Create a Web App on Azure Portal [cite: 22]
* [cite_start]**Step 1: Go to Azure Portal** [cite: 23]
  [cite_start]Visit portal.azure.com and log in to your account[cite: 24].
* [cite_start]**Step 2: Create a Resource** [cite: 25]
  [cite_start]Click "Create a resource" → search for "Web App" → click Create[cite: 26].
* [cite_start]**Step 3: Fill in the App Details** [cite: 27]
  [cite_start]Fill in the form with these settings[cite: 28]:

| Field | Value |
| :--- | :--- |
| Resource Group | [cite_start]Create new → e.g. my-site-rg [cite: 29] |
| [cite_start]Name | e.g. mylinuxsite123 (this becomes your URL) [cite: 29] |
| Publish | [cite_start]Code [cite: 29] |
| Runtime Stack | [cite_start]PHP 8.2 [cite: 29] |
| Operating System | [cite_start]Linux [cite: 29] |
| Region | [cite_start]Central India (or closest to you) [cite: 29] |
| Pricing Plan | [cite_start]Free F1 — Dev/Test [cite: 29] |

* [cite_start]**Step 4: Review and Create** [cite: 30]
  [cite_start]Click "Review + Create" → then "Create"[cite: 31]. [cite_start]Wait approximately 2 minutes for Azure to provision the resource[cite: 31].
* [cite_start]**Step 5: Go to Resource** [cite: 32]
  [cite_start]Once complete, click "Go to resource" to open your Web App[cite: 33].

### [cite_start]Step 3 — Open Kudu File Manager [cite: 34]
* [cite_start]**Step 1: Find the Kudu URL** [cite: 35]
  [cite_start]In your browser, the Azure Portal[cite: 36]. [cite_start]Look for development tools > advance tools > go ➡️ > KUDU webpage open[cite: 37].
* [cite_start]**Step 2: Navigate to File Manager** [cite: 38]
  [cite_start]Navigate to File Site[cite: 39].
* [cite_start]**Step 3: Open the wwwroot folder** [cite: 40]

### [cite_start]Step 4 — Upload Your ZIP File [cite: 41]
* [cite_start]**Step 1: Drag and Drop** [cite: 42]
  [cite_start]At the bottom of the File Manager page you will see: "Drag a Zip File here to extract & upload, or click to select one"[cite: 43].
* [cite_start]**Step 2: Drop your ZIP** [cite: 44]
  [cite_start]Drag your zipped `index.html` file onto that area[cite: 45]. [cite_start]Azure will automatically extract it into the `wwwroot` folder[cite: 45].
* [cite_start]**Step 3: Verify** [cite: 46]
  [cite_start]You should now see your `index.html` listed in the `wwwroot` directory[cite: 47].

### [cite_start]Step 5 — Visit Your Live Website [cite: 48]
* [cite_start]**Step 1: Copy your Default Domain** [cite: 49]
  [cite_start]Go back to Azure Portal → Your Web App → Overview[cite: 50]. [cite_start]Find "Default domain" on the right side[cite: 50].
* [cite_start]**Step 2: Open in Browser** [cite: 51]
  [cite_start]Your live URL will be [cite: 52]
* [cite_start]**Step 3: Done!** [cite: 53]
  [cite_start]Your website is now live and accessible to anyone on the internet[cite: 54].

---

## [cite_start]Important Notes [cite: 55]
* [cite_start]The Free F1 plan has limited resources but is perfect for demos and internship tasks[cite: 56].
* [cite_start]If the site shows a default Azure page, wait 1-2 minutes and refresh — the container may still be starting[cite: 57].
* [cite_start]Make sure `index.html` is at the root of the ZIP file, not inside a subfolder, otherwise the site will not load[cite: 58].
* [cite_start]PHP 8.2 runtime is used because it natively serves static HTML files on Linux without any extra configuration[cite: 59].
* [cite_start]The Kudu File Manager URL uses `.scm.` in the domain — this is the deployment/management endpoint[cite: 60].

## [cite_start]Quick Reference Summary [cite: 61]
[cite_start]The complete deployment process in 5 simple steps[cite: 62]:

| # | Action | Where |
| :--- | :--- | :--- |
| 1 | Zip your file | [cite_start]Your local computer [cite: 63] |
| 2 | [cite_start]Create Web App | portal.azure.com → Create Resource [cite: 63] |
| 3 | [cite_start]Open Kudu File Manager | yourapp.scm.azurewebsites.net/fileManager [cite: 63] |
| 4 | Navigate to site/wwwroot | [cite_start]Kudu File Manager [cite: 63] |
| 5 | Drag & drop ZIP | [cite_start]Bottom of File Manager page [cite: 63] |
