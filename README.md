---
language:
- id
license: cc-by-4.0
size_categories:
- 10K<n<100K
task_categories:
- text-classification
- feature-extraction
tags:
- nlp
- indonesian
- campus-complaints
- student-aspirations
- informal-indonesian
- sentiment-analysis
- named-entity-recognition
- universitas-mercu-buana
configs:
- config_name: default
  data_files:
  - split: train
    path: data/*.csv
---

# 🎓 Indonesian Campus Complaints & Aspirations Corpus

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Language: Indonesian](https://img.shields.io/badge/Language-Indonesian-blue.svg)](https://huggingface.co/languages/id)
[![Repository: Hugging Face](https://img.shields.io/badge/Hugging%20Face-Datasets-orange.svg)](https://huggingface.co/datasets/YogaSWD/indonesian-campus-complaints)

## 📌 Dataset Summary

**Indonesian Campus Complaints & Aspirations Corpus** is a massive, fine-grained, multi-label benchmark dataset capturing the full complexity of contemporary spoken and written informal Indonesian used by university students. 

Originating from research on automated academic complaint triage at **Universitas Mercu Buana (UMB)**, this corpus reflects real-world student interactions ranging from heavy South Jakarta slang (*slang Jaksel / Gen-Z*), SMS/WhatsApp chat abbreviations, QWERTY fat-finger typos, code-switching (*English-Indonesian*), polite formal administrative Indonesian, to academic sarcasm.

---

## 🏗️ Ground Truth Data Annotation Schema (11 Columns)

Each record in the dataset is annotated across 11 standardized ground truth columns:

| Column Name | Type | Description | Example |
|---|---|---|---|
| `id` | String | Unique standard ticket identifier | `BSP-0001` |
| `text_raw` | String | Raw complaint text containing informal vocabulary and synthetic PII | `"Sore min sarpras, ac d d102 mati dr kmrn tlg bgt d bnerin gerah bgt"` |
| `text_masked` | String | Sanitized complaint text with deterministic privacy masking tokens | `"Sore min sarpras, ac d d102 mati dr kmrn tlg bgt d bnerin gerah bgt"` |
| `target_biro` | String | Responsible campus operational unit / bureau | `BSP` (Biro Sarana dan Prasarana) |
| `topic_category` | String | Standard taxonomy category code | `FAS` (Fasilitas & Sarana Prasarana) |
| `core_subject` | String | Synthesized, single-sentence core problem summary | `Pendingin ruangan (AC) di D-102 rusak tidak dingin dan ruangan pengap` |
| `entities_json` | JSON String | Extracted campus entities, buildings, rooms, and issue taxonomy | `{"biro": "BSP", "lokasi_spesifik": "D-102", "jenis_isu": "ac_rusak"}` |
| `evidence_span` | String | Exact verbatim span from the text supporting the classification | `ac bocor` |
| `priority` | String | Actionable triage urgency level | `Tinggi`, `Sedang`, `Rendah` |
| `emotion` | String | Affective emotion / sentiment state of the student | `kecewa`, `frustrasi`, `panik_kesal`, `jijik_kecewa` |
| `linguistic_style` | String | Linguistic register / style category | `slang_jakarta`, `typo_singkatan`, `formal_santun`, `curhat_panjang`, `sarkasme`, `campur_kode` |

---

## 📚 Integrated Authentic Dictionaries (10.372+ Entries)

The dataset is enriched with authentic normalization dictionaries located in the `dictionaries/` folder:
- **`karma_kamus_singkatan_slang.csv`** (10,372 entries): Slang Gen-Z, QWERTY typos, consonant abbreviations, and 740+ bureau-specific authentic phrases.
- **`karma_aturan_pola_normalisasi.csv`** (62 regex rules): Text deformation and vowel-omission normalization rules.
- **`karma_pola_imbuhan_informal.csv`** (498 patterns): Informal affixation patterns (*-in, nge-, di-...-in*).
- **`karma_leksikon_sensitif.csv`** (1,037 entries): Mental health, bullying, and safety lexicon (*Academic Research Only*).

---

## 🚀 Quickstart: Loading the Dataset in Python

You can load this dataset with one line of code using the Hugging Face `datasets` library:

```python
from datasets import load_dataset

# Load full campus complaints dataset
dataset = load_dataset("YogaSWD/indonesian-campus-complaints")

print(dataset["train"][0])
```

---

## 🔒 Ethics, Privacy, and Responsible AI

1. **Zero Real PII**: No real student identities, National Student IDs (NIM), private phone numbers, or actual personal emails exist in this dataset. All personal details are either synthetically generated or deterministic anonymization tokens (`[NAMA]`, `[NIM]`, `[NO_HP]`).
2. **Harm Reduction**: Explicit or graphic descriptions of sexual violence/trauma are strictly excluded. Sensitive cases focus on procedural policy inquiries, counseling access, and institutional support mechanisms.
3. **Research-Only**: This corpus is distributed under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** license.

---

## ✍️ Citation & Authors

If you use this dataset or the accompanying dictionaries in your research, please cite:

```bibtex
@dataset{karma_indonesian_campus_complaints_2026,
  author    = {Yoga Gusti Rachmadi and Haikal and Lukman},
  title     = {Indonesian Campus Complaints & Aspirations Corpus: A Multi-Label Fine-Grained Benchmark for Informal Indonesian NLP},
  year      = {2026},
  publisher = {Hugging Face},
  institution = {Universitas Mercu Buana (UMB)},
  url       = {https://huggingface.co/datasets/YogaSWD/indonesian-campus-complaints}
}
```
