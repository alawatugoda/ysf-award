# YSF Report Generator

A self-evaluation tool for the **Young Scientist Award for Research** (YSF), administered by the Young Scientists' Forum of Sri Lanka.

## What it does

- Fetches your publications automatically from [OpenAlex](https://openalex.org/) using your Author ID
- Classifies each paper into the correct YSF scoring category (§1.1–§1.8) using Scimago journal rankings
- Calculates your total score across all four sections
- Lets you add papers manually (non-indexed journals, conference abstracts, books, etc.)
- Generates a print-ready report matching the official YSF application format

## Files

| File | Description |
|---|---|
| `ysf_report.html` | Main tool — open in any browser |
| `scimago_issn.json` | Scimago 2025 journal rankings (ISSN → Quartile) |
| `scimagojr_2025.csv` | Source CSV for the Scimago data |

> **Both files must be in the same folder** for quartile detection to work.

## How to use

1. Download both files and place them in the same folder
2. Open `ysf_report.html` in your browser
3. Enter your **OpenAlex Author ID** (e.g. `A5056029451`) and click **Fetch**
4. Review and adjust the classifications as needed
5. Add any missing papers manually using the **Add Paper** section
6. Click **🖨️ Print / PDF** to generate the report

## Sections

| Section | Criteria | Points |
|---|---|---|
| §1.1 | Q1/Q2 Journals | 6 pts (×2 if 1st/Corr) |
| §1.2 | Q3/Q4 Journals | 4 pts (×2 if 1st/Corr) |
| §1.3 | Other Indexed Journals | 2 pts (×2 if 1st/Corr) |
| §1.4 | Non-indexed Journals | 1.5 pts (Max 15) |
| §1.5 | Conference Papers | 1 pt (Max 10) |
| §1.6 | Conference Abstracts | 0.5 pts (Max 10) |
| §1.7 | Books | 3 pts (×2 if 1st/Corr) |
| §1.8 | Book Chapters | 2 pts (×2 if 1st/Corr) |

## Eligibility

- **Section 1 (R&D)**: minimum 50 points
- **Section 2 (Outreach)**: minimum 20 points
- **Total**: minimum 70 points

## Saving your data

Use **💾 Save JSON** to export your data as a JSON file. Use **📂 Load JSON** to restore it later. Data is not saved in the browser — always save before closing.

## Scimago data updates

The `scimago_issn.json` file is updated automatically every month via a GitHub Actions workflow. If you are using the tool locally, download the latest file from the repository.

To manually update:
1. Download the latest CSV from [scimagojr.com/journalrank.php](https://www.scimagojr.com/journalrank.php)
2. Upload it to this repository as `scimagojr_YYYY.csv`
3. Go to **Actions → Update Scimago Data → Run workflow**

## Live version

**[https://alawatugoda.github.io/ysf-award/ysf_report.html](https://alawatugoda.github.io/ysf-award/ysf_report.html)**

---

*Based on UGC Circular No. 05/2018 and YSF scoring guidelines.*
