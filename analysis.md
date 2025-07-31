# Evaluating LLM Performance on Syracuse Women's Lacrosse Data (2023–2025)

## 1. Overview

This research evaluates how three Large Language Models (LLMs)—ChatGPT, Claude, and Google AI Search—perform when answering natural language questions about structured sports statistics. The dataset includes Syracuse Women's Lacrosse team data for the 2023, 2024, and 2025 seasons, sourced from [cuse.com](https://cuse.com/sports/2013/1/16/WLAX_0116134638).

The aim was to test:

- Accuracy on direct factual queries
- Ability to perform reasoning-based calculations
- Handling of analytical or predictive questions
- Limitations when data is partially available or OCR-processed

---

## 2. Dataset

- **Seasons:** 2023, 2024, 2025
- **Format:** PDF files (converted to images for testing)
- **Data contained:**
  - Team-level statistics: games played, goals, shots, saves, clears, turnovers
  - Player-level statistics: goals, assists, points, turnovers (available in 2023, partially in 2025)
  - Game-by-game results with opponent rankings

### Limitations:

- 2024 data lacked player-level breakdowns
- 2025 data had inconsistencies in parsing when processed by some LLMs
- OCR from PDFs to text likely introduced recognition errors for some models

---

## 3. Methodology

A set of questions was designed across three levels of complexity:

1. **Basic factual retrieval**
2. **Intermediate reasoning** (aggregation, filtering)
3. **Advanced analytical insights** (derived metrics, subjective judgments)

Each model was prompted with the same questions using the PDF/image data provided. Responses were compared to manually validated answers derived from the dataset.

---

## 4. Results

### 4.1 Basic Retrieval Questions

| Question | ChatGPT | Claude | Google | Ground Truth |
|----------|---------|--------|--------|--------------|
| Games played per season (2023–2025) | 21, 22, 19 | 21, 22, 19 | 21, 22, 19 | 21, 22, 19 |
| Win-loss record each year | 18-3, 16-6, 10-9 | 18-3, 16-6, 10-9 | 18-3, 16-6, 10-9 | 18-3, 16-6, 10-9 |
| Top scorer each season | Incorrect for 2023, no data for 2024-25 | Correct 2023 only | Correct all years | Meaghan Tyrrell (2023), Emma Tyrrell (2024), Emma Ward (2025) |

**Observation:** Google was the most reliable, likely due to access to structured external data. ChatGPT and Claude occasionally failed due to OCR errors or missing player stats.

---

### 4.2 Intermediate Reasoning

**Question:** Who had the highest total points (G+A) in 2024?

- **ChatGPT:** Unable to answer (no individual stats parsed)
- **Claude:** Same limitation
- **Google:** Correctly answered Emma Tyrrell with 92 points (70G, 22A)

Intermediate questions requiring derived data were only answered accurately by Google, suggesting stronger ability to supplement missing dataset info or better parsing capabilities.

---

### 4.3 Advanced Analytical Question

**Question:** How did Syracuse's performance against top-10 teams evolve from 2023–2025?

- **ChatGPT:** 5-3 (2023), 6-5 (2024), 3-5 (2025) → Declining trend
- **Claude:** 5-2 (2023), 5-3 (2024), 2-5 (2025) → Declining trend
- **Google:** 7-3 (2023), 3-4 (2024), 2-5 (2025) → Declining trend, more detailed breakdown

All models identified the downward trend, but Google provided more granular results, citing individual games. ChatGPT and Claude sometimes misclassified ranked opponents due to OCR or interpretation issues.

---

## 5. Analysis of LLM Limitations

1. **Parsing Issues:** PDFs converted to images likely hindered ChatGPT and Claude's ability to read tables accurately
2. **Missing Data:** Lack of player-level stats in 2024 and partial data in 2025 limited LLM responses unless supplemented by external knowledge
3. **Computation Gaps:** Models without explicit structured data struggled with aggregation and derived metrics
4. **External Knowledge Advantage:** Google's broader data access allowed accurate answers even when provided files lacked detail

---

## 6. Conclusion

- **Google** outperformed ChatGPT and Claude on all question types, particularly intermediate and advanced reasoning questions
- **ChatGPT and Claude** relied solely on parsed PDFs, failing where data was incomplete or OCR errors occurred
- For high-accuracy question answering on structured datasets, LLMs benefit significantly from:
  - Clean, structured (CSV/JSON) input instead of images/PDFs
  - Clear, well-defined metrics for complex queries
  - Supplementary external knowledge when dataset gaps exist

### Future Work

- Compare results when providing CSV instead of PDF/image to isolate OCR parsing errors
- Extend test questions to predictive analytics tasks
- Evaluate model consistency when the dataset grows larger or more unstructured
