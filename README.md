# 🎓 Indonesian Campus Complaints & Aspirations Corpus (44K)
### *A Massive Multi-Style Benchmark for Informal Indonesian NLP, Intent Routing, and Affective Computing*

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Language: Indonesian](https://img.shields.io/badge/Language-Indonesian-blue.svg)](https://huggingface.co/languages/id)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Datasets-orange.svg)](https://huggingface.co/datasets/YogaSWD/indonesian-campus-complaints)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black.svg)](https://github.com/YogUNI/indonesian-campus-complaints)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF.svg)](https://www.kaggle.com/datasets/yogagustirachmadi/indonesian-campus-complaints)
[![Institution: Universitas Mercu Buana](https://img.shields.io/badge/Institution-Universitas%20Mercu%20Buana-navy.svg)](https://mercubuana.ac.id)

---

## 📌 1. Scientific Context & Motivation

Indonesia is home to over 275 million people, and its digital sphere is characterized by intense linguistic fluidity. In higher education, student communication occurs through high-velocity informal channels (WhatsApp groups, student portals, social media) dominated by:
- **South Jakarta (*Jaksel*) Colloquialisms & Gen-Z Slang**: rapid borrowing and code-switching (*"literally"*, *"overthinking"*, *"validasi"*, *"anw"*).
- **Vowel Omission & Text Messaging Acronyms**: aggressive shorthand (*"tlg bgt d bnerin"*, *"dr kmrn kls ga dingin"*).
- **QWERTY Fat-Finger Typos**: mechanical errors common in mobile chat environments.
- **Dynamic Informal Affixation**: productive non-standard morphology (*"-in"*, *"nge-"*, *"ke-...-an"*).
- **Academic Sarcasm & Affective Venting**: emotionally charged grievances requiring nuanced intent extraction.

Traditional Indonesian NLP corpora (e.g., Indo4B, Kompas, Tempo) are overwhelmingly skewed toward formal journalistic prose. As a result, state-of-the-art multilingual LLMs (e.g., GPT-4, Gemini) frequently misinterpret colloquial complaints, failing to route critical student grievances to the correct institutional bureau.

The **Indonesian Campus Complaints & Aspirations Corpus** bridges this critical gap. Originating from research on automated academic complaint triage at **Universitas Mercu Buana (UMB)**, this benchmark provides **44,550 meticulously curated, zero-PII records** across **11 campus bureaus**, enriched with **11 ground truth annotation columns** and **10,372+ authentic normalization lexicon entries**.

---

## 📊 2. Dataset Architecture & Annotation Schema (11 Columns)

Every sample in the corpus is structured with 11 ground truth columns designed for multi-task evaluation:

| Column Name | Type | Description | Authentic Example |
|:---|:---|:---|:---|
| `id` | String | Standardized unique ticket ID | `BSP-0001` |
| `text_raw` | String | Raw informal text with authentic slang, typos, and abbreviations | `"Sore min sarpras, ac d d102 mati dr kmrn tlg bgt d bnerin gerah bgt"` |
| `text_masked` | String | Sanitized text with deterministic privacy-preserving tokens | `"Sore min sarpras, ac d d102 mati dr kmrn tlg bgt d bnerin gerah bgt"` |
| `target_biro` | String | Responsible campus bureau (11 classes) | `BSP` (Biro Sarana dan Prasarana) |
| `topic_category` | String | High-level campus taxonomy code | `FAS` (Fasilitas & Sarana Prasarana) |
| `core_subject` | String | Synthesized 1-sentence declarative core issue statement | `Pendingin ruangan (AC) di D-102 rusak tidak dingin dan ruangan pengap` |
| `entities_json` | JSON String | Extracted campus entities, buildings, rooms, and issue types | `{"biro": "BSP", "lokasi_spesifik": "D-102", "jenis_isu": "ac_rusak"}` |
| `evidence_span` | String | Verbatim textual evidence supporting the classification | `ac d d102 mati` |
| `priority` | String | Actionable urgency triage level (`Tinggi`, `Sedang`, `Rendah`) | `Sedang` |
| `emotion` | String | Affective student emotional state | `frustrasi`, `kecewa`, `panik_kesal`, `jijik_kecewa` |
| `linguistic_style` | String | Register / style variation category | `slang_jakarta`, `typo_singkatan`, `formal_santun`, `curhat_panjang`, `sarkasme`, `campur_kode` |

---

## 🏛️ 3. Institutional Bureau Coverage (11 Classes • 4,050 Samples Each)

The corpus covers the complete operational jurisdiction of higher education administration:

| Bureau Code | Official Bureau Name | Remit & Issue Domains | Samples |
|:---|:---|:---|:---:|
| **BAP** | Biro Administrasi Pembelajaran | KRS, jadwal kuliah, transkrip, yudisium, remedial, dosen pengganti | 4,050 |
| **ULT** | Unit Layanan Terpadu | Legalisir ijazah, surat keterangan mahasiswa aktif, helpdesk terpadu | 4,050 |
| **BPM** | Biro Penjaminan Mutu | Evaluasi dosen (EDOM), mutu kurikulum, standar akreditasi fakultas | 4,050 |
| **BSP** | Biro Sarana dan Prasarana | AC rusak, proyektor mati, lift mati, kebersihan toilet, parkiran | 4,050 |
| **BTI** | Biro Teknologi Informasi | Portal SIA error, server down, WiFi lambat, akun SSO, reset password | 4,050 |
| **BAK** | Biro Administrasi Keuangan | Tagihan VA bank, cicilan SPP/UKT, beasiswa, denda keterlambatan | 4,050 |
| **DITMAWA** | Direktorat Kemahasiswaan | Ormawa, proposal kegiatan UKM, SKPI, kompetisi nasional, dana kegiatan | 4,050 |
| **PPKS** | Satgas Pencegahan & Penanganan Kekerasan Seksual | Alur pelaporan aman, pendampingan psikologis, perlindungan saksi *(Sterilized)* | 4,050 |
| **HUMAS** | Biro Hubungan Masyarakat | Media sosial kampus, kalender libur resmi, publikasi prestasi, flyer hoax | 4,050 |
| **PERPUS** | Perpustakaan & Riset | Akses e-journal ScienceDirect/IEEE, peminjaman buku, ruang baca tesis | 4,050 |
| **BKP** | Biro Konseling & Pengembangan Karir | Konseling stres skripsi/burnout, magang MSIB, tracer study alumni | 4,050 |
| **TOTAL** | **11 Campus Bureaus** | **Balanced Stratified Multiclass Benchmark** | **44,550** |

---

## 🗣️ 4. Six Authentic Linguistic Registers

1. **Slang Jakarta / Jaksel (`slang_jakarta`)**: Heavy colloquial vocabulary (*"Gue/elo"*, *"spill"*, *"literally overthinking"*, *"gaspol"*).
2. **Typo & Singkatan Chat (`typo_singkatan`)**: Heavy text messaging shorthand and QWERTY fat-finger errors (*"klo mnrt sy bgtu tlg ya min fastresp"*, *"ac kls d102 bocor"*).
3. **Formal & Santun Administratif (`formal_santun`)**: Polite, respectful academic communication (*"Selamat siang Bapak/Ibu pengelola sarana prasarana..."*).
4. **Curhat Panjang / Affective Venting (`curhat_panjang`)**: Multi-sentence narrative expressing frustration or mental exhaustion before stating the core problem.
5. **Sarkasme Kampus (`sarkasme`)**: Witty, satirical irony criticizing campus facilities (*"Wah keren banget lift kampus berasa sauna gratis tiap hari..."*).
6. **Campur Kode / Code-Switching (`campur_kode`)**: Mixed Indonesian-English discourse common in contemporary university environments.

---

## 📚 5. Authentic Normalization Lexicons (10,372+ Entries)

The dataset is bundled with authentic linguistic resource files in the `dictionaries/` folder:
- **`karma_kamus_singkatan_slang.csv`** (10,372 entries): Mapping of informal slang, abbreviations, and chat typos to formal Indonesian equivalents.
- **`karma_aturan_pola_normalisasi.csv`** (62 regex rules): Phonological and orthographic deformation transformation rules.
- **`karma_pola_imbuhan_informal.csv`** (498 patterns): Non-standard suffix and prefix mappings (*-in*, *nge-*, *ke-...-an*).
- **`karma_leksikon_sensitif.csv`** (1,037 entries): Critical safety and psychological distress lexicon for triage escalation.

---

## 🔬 6. Empirical Benchmark Baselines

Rigorous baseline evaluation was conducted on local developer hardware (**Intel Core i7-12650H & NVIDIA GeForce RTX 4060 Laptop GPU 8GB GDDR6**):

| Model Architecture | Parameters | Triage Accuracy | Macro F1-Score | Inference Latency | Local / Cloud |
|:---|:---:|:---:|:---:|:---:|:---:|
| **IndoBERT Base Fine-Tuned** (`indobert-base-uncased`) | 124M | **100.00%** | **1.0000** | ~14 ms | Local GPU |
| **Linear SVM** (TF-IDF Word + Char N-Grams) | N/A | **99.99%** | **0.9999** | **~2 ms** | Local CPU |
| **Multinomial Naive Bayes** | N/A | **99.64%** | **0.9964** | **~1 ms** | Local CPU |
| **Google Gemini 2.5 Flash / 1.5** (Zero-Shot) | Frontier LLM | **60.85%** | **0.5982** | ~1,850 ms | Cloud API |

> 💡 **Key Scientific Finding**: Domain-adapted smaller local models (IndoBERT and Linear SVM) vastly outperform generic frontier LLMs on localized informal Indonesian vernacular while offering sub-15ms latency, zero API costs, and total data privacy.

---

## 💡 7. Research Tasks & Use Cases

1. **Extreme Informal Indonesian Text Classification**: Benchmarking transformer models on heavily mutated colloquial texts.
2. **Intent Classification & Automated Triage**: Multi-class routing for institutional and customer support tickets.
3. **Core Subject Abstractive Summarization**: Distilling convoluted student vents into concise, actionable summaries.
4. **Affective Computing & Urgency Scoring**: Detecting student distress, panic, and operational priority.
5. **Named Entity Recognition (NER)**: Extracting room numbers, buildings, campus infrastructure, and course codes.

---

## 🔒 8. Ethics, Privacy & Sanitization Gateway

- **Zero Real PII**: No real student identities, National Student IDs (NIM), private phone numbers, or actual personal emails exist in this dataset. All personal details are either synthetically generated or deterministic anonymization tokens (`[NAMA]`, `[NIM]`, `[NO_HP]`).
- **Sterilized Sensitive Cases (PPKS)**: Explicit trauma narratives are strictly prohibited. Sensitive cases are restricted to formal procedural inquiries, counseling access, witness protection, and policy questions.
- **License**: Distributed under the **Creative Commons Attribution 4.0 International (CC-BY-4.0)** license.

---

## ✍️ 9. Citation & Authors

If you utilize this benchmark dataset or lexicons in your scientific research, please cite:

```bibtex
@dataset{rachmadi2026karma,
  author    = {Yoga Gusti Rachmadi and Haikal and Lukman},
  title     = {Indonesian Campus Complaints & Aspirations Corpus: A Massive Multi-Style Benchmark for Informal Indonesian NLP},
  year      = {2026},
  publisher = {Kaggle / Hugging Face},
  institution = {Universitas Mercu Buana (UMB)},
  doi       = {10.34740/KAGGLE/DS/12814376},
  url       = {https://www.kaggle.com/datasets/yogagustirachmadi/indonesian-campus-complaints}
}
```
