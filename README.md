# Vetology AI - Radiology Report Evaluator

A Python application for evaluating veterinary thoracic radiology reports using Google Gemini LLMs and generating confusion matrix performance metrics against radiologist ground truth.

Repository: [https://github.com/ramanasuddala143-code/vetology_main.git](https://github.com/ramanasuddala143-code/vetology_main.git)

---

## Quick Setup

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Configure your Gemini API key in `.env`:**
   ```env
   GEMINI_API_KEY=your_api_key_here
   GEMINI_MODEL=gemini-3.1-flash-lite
   ```

---

## How to Run

* **Run live evaluation on 100 reports:**
  ```bash
  python app.py --limit 100
  ```

* **Test on 5 reports:**
  ```bash
  python app.py --limit 5
  ```

* **Run offline dry-run (no API credits used):**
  ```bash
  python app.py --dry-run --limit 100
  ```

---

## Project Structure

| File | Description |
|:---|:---|
| `app.py` | Main script: loads Excel reports, calls Gemini API, and builds confusion matrix |
| `requirements.txt` | Minimal Python dependencies (`google-genai`, `pandas`, `openpyxl`, `dotenv`) |
| `prompt_log.md` | Week 3 prompt engineering log tracking prompt iterations and failure modes |
| `.gitignore` | Prevents uploading confidential `.xlsx` patient data and `.env` keys to GitHub |
| `README.md` | Project summary and usage instructions |

---

## Output

The script outputs `Confusion_Matrix_Canine_Thorax.xlsx` matching the official Vetology evaluation format:
* Per-condition **True Positives (TP)**, **False Negatives (FN)**, **True Negatives (TN)**, and **False Positives (FP)**
* Dynamic Excel formulas for **Sensitivity**, **Specificity**, and **Agreement Rate**

---

*Note: All proprietary radiology `.xlsx` datasets are kept local and excluded from git version control.*
