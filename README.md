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

## Citation

If you use the **STAR-IL dataset**, please cite our paper:

```bibtex
@inproceedings{shetye-etal-2026-star,
  title     = {STAR-IL: A Dataset for Style-Aware Machine Translation of Product Reviews in Indian Languages},
  author    = {Shetye, Ketaki and Sharma, Dipti Misra and Krishnamurthy, Parameswari},
  booktitle = {Proceedings of the Fifteenth Language Resources and Evaluation Conference (LREC 2026)},
  month     = may,
  year      = {2026},
  pages     = {8780--8793},
  address   = {Palma, Mallorca, Spain},
  publisher = {European Language Resources Association (ELRA)},
  doi       = {10.63317/4oq85vioi2tu},
  abstract  = {Product reviews on e-commerce platforms are a critical form of user-generated content influencing consumer decisions. However, these reviews are predominantly in English, creating accessibility barriers for non-fluent users. Existing translation models often fail to preserve domain-specific features and colloquial style, resulting in unnatural outputs. To address this, we introduce STAR-IL, a human-annotated multilingual parallel corpus for style-aware translation of product reviews. Experiments show that models fine-tuned on STAR-IL achieve an average improvement of 5.77 BLEU and 3.78 COMET points over baselines across all languages. The dataset is publicly available at https://github.com/ltrc/STAR-IL-Corpus.}
}


