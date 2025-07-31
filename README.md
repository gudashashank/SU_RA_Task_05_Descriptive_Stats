# LLM Performance Evaluation: Sports Statistics Analysis

A comparative study evaluating how different Large Language Models (LLMs) handle structured sports data analysis and natural language queries.

## 🏆 Project Overview

This research project compares the performance of three major LLMs—**ChatGPT**, **Claude**, and **Google AI Search**—in analyzing Syracuse Women's Lacrosse statistics from 2023-2025. The study tests each model's ability to extract information, perform calculations, and provide analytical insights from PDF-based sports data.

## 📊 Key Findings

- **Google AI Search** consistently outperformed other models across all question types
- **OCR parsing issues** significantly impacted ChatGPT and Claude's accuracy
- **External knowledge access** provided substantial advantages for complex queries
- **Structured data formats** (CSV/JSON) are crucial for reliable LLM performance

## 🎯 Research Objectives

- Evaluate LLM accuracy on direct factual queries
- Test reasoning capabilities for data aggregation and filtering
- Assess performance on analytical and predictive questions
- Identify limitations when working with partially available or OCR-processed data

## 📁 Dataset

**Source:** [Syracuse University Athletics](https://cuse.com/sports/2013/1/16/WLAX_0116134638)

**Coverage:** 2023, 2024, 2025 seasons

**Data Types:**
- Team-level statistics (games, goals, shots, saves, clears, turnovers)
- Player-level statistics (goals, assists, points, turnovers)
- Game-by-game results with opponent rankings

**Format:** PDF files converted to images for testing

## 🔬 Methodology

### Question Categories
1. **Basic Retrieval** - Direct factual queries
2. **Intermediate Reasoning** - Data aggregation and filtering
3. **Advanced Analytics** - Derived metrics and subjective analysis

### Testing Process
- Identical questions posed to each LLM
- PDF/image data provided as input
- Responses validated against manually verified ground truth
- Performance compared across accuracy and detail metrics

## 📈 Results Summary

### Basic Retrieval Performance
| Metric | ChatGPT | Claude | Google |
|--------|---------|--------|--------|
| Games per season | ✅ | ✅ | ✅ |
| Win-loss records | ✅ | ✅ | ✅ |
| Top scorers | ❌ | ⚠️ | ✅ |

### Advanced Analysis
- **Trend Analysis:** All models identified performance decline vs. top-10 teams
- **Data Gaps:** Only Google successfully handled missing player statistics
- **Computation:** Google excelled at derived metrics and aggregations

## 🚧 Limitations Identified

1. **OCR Parsing Issues** - PDF-to-text conversion errors
2. **Missing Data Handling** - Incomplete player statistics in some seasons
3. **Computation Gaps** - Difficulty with aggregation without structured input
4. **External Knowledge Dependency** - Advantage for models with broader data access

## 🔮 Future Research

- [ ] Test performance with CSV/JSON vs. PDF inputs
- [ ] Expand to predictive analytics tasks
- [ ] Evaluate consistency with larger, more complex datasets
- [ ] Compare performance across different sports and data types

## 🛠️ Technical Stack

- **Data Sources:** PDF documents, web scraping
- **Analysis Tools:** Manual validation, comparative evaluation
- **Models Tested:** ChatGPT, Claude, Google AI Search

## 🤝 Contributing

Interested in extending this research? Contributions welcome for:
- Additional LLM comparisons
- Different sports datasets
- Enhanced evaluation metrics
- Automated testing frameworks

## 📄 License

This project is available under the MIT License. See LICENSE file for details.

## 📧 Contact

For questions about this research or collaboration opportunities, please open an issue in this repository.

---

**Keywords:** Large Language Models, Sports Analytics, Data Analysis, OCR, Natural Language Processing, Performance Evaluation
