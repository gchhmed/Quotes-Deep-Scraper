# 🕵️‍♂️ Quotes Intelligence & Deep-Bio Scraper (v2.0)

An advanced, production-ready web scraping engine built with **Python**. This version features **Global Tag Discovery**, allowing users to see every available category across the entire website before choosing their preferences.

---

## 🎯 What's New in V2.0?

The latest update focuses on **User Experience (UX)** and **Data Integrity**:

* **Global Tag Discovery:** The engine now performs a pre-scan of all 10 pages to collect a unique, sorted set of tags using Python `sets`.
* **Intelligent Text Wrapping:** Utilizing the `textwrap` library, the available tags are displayed in a clean, readable paragraph format in the console.
* **Case-Insensitive Matching:** Enhanced filtration logic that handles variations in user input (e.g., "Life" vs "life") for 100% match accuracy.
* **Data Sanitization:** Improved string stripping to handle invisible whitespaces in both website tags and user inputs.

---

## 🛠 Technical Highlights

* **The Pagination Engine:** A dynamic `while` loop that traverses the site by detecting the "Next" button, ensuring it works even if the number of pages changes.
* **Data Engineering (Location Parser):** A custom logic that breaks down "Born Location" into a structured **City | State | Country** schema, regardless of the number of commas in the source string.
* **Efficiency:** Uses conditional HTTP requests; biographical data is only fetched if the user explicitly requests it, optimizing bandwidth.

---

## 📊 Data Structure (The "Feast")

The output is a structured CSV file with the following schema:

| Field | Description |
| :--- | :--- |
| **Full Name** | The verified name of the author. |
| **Quote** | The extracted text of the quote. |
| **Related Tags** | Comma-separated categories associated with the quote. |
| **Born Date** | Extracted and sanitized birth date. |
| **City** | Parsed city of birth. |
| **State** | Parsed state (Defaults to 'Unknown' if not applicable). |
| **Country** | Parsed country (Extracted via reverse-index logic). |
| **Biography** | A 100-character preview of the author's biography. |

---

## 🚀 Installation & Usage

### 1. Clone the repository
```bash
git clone [https://github.com/yourusername/quotes-intelligence-scraper.git](https://github.com/yourusername/quotes-intelligence-scraper.git)
cd quotes-intelligence-scraper
