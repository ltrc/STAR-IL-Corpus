# STAR-IL-Corpus: A Dataset for Style-Aware Machine Translation of Product Reviews in Indian Languages

Welcome to the official repository for the **STAR-IL: Style-Aware Machine Translation of Product Reviews in Indian Languages** dataset.

## Overview

STAR-IL is a novel, human-annotated parallel corpus with over 55000 samples covering English-to-Indian Language machine translation, specifically designed to address the challenge of **style preservation** in translation of product reviews. The dataset captures the colloquial, code-mixed, and domain-specific language inherent in online product reviews. It covers eight languages, namely, Hindi, Marathi, Bengali, Gujarati, Urdu, Kannada, Tamil, and Telugu.

## Repository Structure

The dataset is organized into distinct directories corresponding to the source data, translated data, and annotation guidelines:

```
STAR-IL-Corpus/
├── guidelines/
│   └── guidelines.pdf          # Instructions used by human annotators for translating reviews
├── source_data/
│   ├── benchmark/              # Raw source reviews (TXT) for both fashion and electronics domains
│   └── training/               # Raw source reviews (TXT) for both fashion and electronics domains
└── translated_data/
    ├── benchmark/              # Translated reviews (CSV) across 8 target languages
    └── training/               # Translated reviews (CSV) across 8 target languages

```

## Data Format

All CSV files follow the same column structure:

| Column | Description |
| :--- | :--- |
| `src` | The English product review (Source Text). |
| `tgt` | The corresponding human-annotated, style-aware target language translation. |
| `src_lang` | Language code for Source (always `English`). |
| `tgt_lang` | Language code for Target (e.g., `Hindi`, `Bengali`, `Tamil`, etc.). |
| `domain` | Product category `E`(`electronics`) or `F`(`fashion`). |

## Quick Start

You can easily load and explore the dataset using Python and Pandas:

```
import pandas as pd

# Load the benchmark dataset for a specific language (e.g., Marathi)
df_marathi = pd.read_csv("translated_data/benchmark/Marathi.csv")

# View the first few style-aware translations
print(df_marathi[['src', 'tgt', 'domain']].head())
```

<!-- ## Citation

If you use the STAR-IL dataset or benchmark in your research, please cite our paper: -->

<!-- ## License -->


