# YSF Report Generator

[![Ko-fi](https://img.shields.io/badge/Support-Ko--fi-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/araliya)

A self-evaluation tool for the **Young Scientist Award for Research** (YSF), administered by the Young Scientists' Forum of Sri Lanka.

## What it does

- Fetches your publications automatically from [OpenAlex](https://openalex.org/) using your Author ID
- Classifies each paper into the correct YSF scoring category (§1.1–§1.8) using Scimago journal rankings
- Calculates your total score across all four sections with caps and multipliers
- Lets you add manual items for §1.9–§1.22, §2, §3, §4 — with editable role, scope and pts directly in the screen table
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
6. Fill in §1.9–§1.22, §2, §3, §4 items using the sidebar input lists
7. Click **🖨️ Print / PDF** to generate the report

## Sections

### §1 — Research & Development (Publications)

| Section | Criteria | Base pts | 1st/Corr | Cap |
|---|---|---|---|---|
| §1.1 | Q1/Q2 Journals | 6 | ×2 = 12 | — |
| §1.2 | Q3/Q4 Journals | 4 | ×2 = 8 | — |
| §1.3 | Other Indexed Journals | 2 | ×2 = 4 | — |
| §1.4 | Non-indexed Journals | 1.5 | ×2 = 3 | 15 pts |
| §1.5 | Conference Papers | 1 | ×2 = 2 | 10 pts |
| §1.6 | Conference Abstracts | 0.5 | ×2 = 1 | 10 pts |
| §1.7 | Books | 3 | ×2 = 6 | — |
| §1.8 | Book Chapters | 2 | ×2 = 4 | — |

### §1 — Other Research Activities (manual)

| Section | Criteria | Pts |
|---|---|---|
| §1.9 | Member/Editor — Indexed publication | 4 (Assoc. ×1.5, Chief ×2) |
| §1.10 | Member/Editor — Non-indexed publication | 2 (Assoc. ×1.5, Chief ×2) |
| §1.11 | Reviewer — Indexed journals | 1 (max 4 pts) |
| §1.12 | Reviewer — Non-indexed journals | 0.5 (max 2 pts) |
| §1.13 | International Research Award | 6 |
| §1.14 | National Research Award | 4 |
| §1.15 | University/Institutional Award | 2 (max 6 pts) |
| §1.16 | International Research Grant | 4 |
| §1.17 | National Research Grant | 3 |
| §1.18 | University/Institutional Grant | 2 |
| §1.19 | Supervision — Ph.D. | 4 (Principal), 2 (Other) |
| §1.20 | Supervision — M.Phil. | 2 (Principal), 1 (Other) |
| §1.21 | Supervision — MSc. | 1 (Principal), 0.5 (Other) |
| §1.22 | Patent | 5 (max 10 pts) |

### §2 — Science Communication & Outreach

| Section | Criteria | Local | Intl | Cap |
|---|---|---|---|---|
| §2.1 | Main coordinator/organizer | 3 | 4.5 | max 9 |
| §2.2 | Other organizing position | 2 | 3 | max 6 |
| §2.3 | Session chair | 0.5 | 0.75 | max 5 |
| §2.4 | Newsletter/magazine article | 0.5 | — | max 3 |
| §2.5 | Resource person | 1 | — | max 5 |
| §2.6 | Community/professional activities | 1 | — | max 5 |
| §2.7 | Professional membership | 1 | — | max 5 |
| §2.8 | UGC Research Performance Tier | T4*=10, T4=8, T3=6, T2=4 | — | — |

### §3 — National Service (max 10 pts)

| Section | Criteria | Pts |
|---|---|---|
| §3.1 | National level policy development | 3 |
| §3.2 | Member of national committee | 2 |

### §4 — International Service (max 10 pts)

| Section | Criteria | Pts |
|---|---|---|
| §4.1 | International level policy development | 4 |
| §4.2 | Member of international committee | 3 |

## Screen table features

- **# | Pts | Description | Role/Scope** — consistent column order across all sections
- **Pts field** — editable directly in the screen table
- **Role dropdown** — §1.9/§1.10: select Member / Assoc. Editor / Chief Editor (auto-updates pts)
- **Principal/Other toggle** — §1.19–§1.21: click to switch role (auto-updates pts)
- **Local/Intl toggle** — §2.1–§2.3: click to switch scope (auto-updates pts)
- **Section ribbons** — each section header shows total pts on the right

## Eligibility

- **Section 1 (R&D)**: minimum 50 points
- **Section 2 (Outreach)**: minimum 20 points, maximum 45 points
- **Total**: minimum 70 points

## Saving your data

Use **💾 Save** to export your data as a JSON file. Use **📂 Open** to restore it later. Data is **not** saved in the browser — always save before closing.

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
