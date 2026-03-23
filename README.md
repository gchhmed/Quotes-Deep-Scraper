# Quotes-Deep-Scraper
"A dynamic Python web scraper that performs deep data extraction with multi-page navigation and intelligent location parsing."

# 🕵️‍♂️ Quotes Intelligence & Deep-Bio Scraper

An advanced, production-ready web scraping engine built with **Python**. This tool doesn't just scrape quotes; it performs **conditional deep-crawling** to harvest rich biographical data, featuring a custom-built **Data Engineering** logic to sanitize and structure geographical information.

---

## 🎯 Project Overview

The main challenge of this project was navigating the trade-off between speed and depth. The script implements a "User-Intent" architecture where it only performs secondary HTTP requests to author bio pages if the user explicitly requests it, saving bandwidth and resources.

### 🛠 Technical Highlights:
* **The Pagination Engine:** A robust `while` loop logic that detects the "Next" button dynamically to traverse all 10 pages without getting trapped in infinite loops.
* **Location Intelligence:** A specialized parser that cleans "Born Location" strings (e.g., removing "in " prefixes) and maps them into a strict **City | State | Country** schema.
* **Smart Filtering:** Real-time filtration based on user-provided tags using Python's `any()` logic.

---

## 📊 Data Structure (The "Feast")

The output is a meticulously organized CSV file. Below is how the data is structured:

| Field | Description |
| :--- | :--- |
| **Full Name** | The verified name of the author. |
| **Quote** | The extracted text of the quote. |
| **Related Tags** | A comma-separated list of categories. |
| **Born Date** | Extracted and cleaned birth date. |
| **City** | Parsed city of birth. |
| **State** | Parsed state/province (Defaults to 'Unknown' if unavailable). |
| **Country** | Parsed country (Handled via reverse-index parsing). |
| **Biography** | A preview of the author's life (First 100 characters). |
