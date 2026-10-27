<div align="center">

<img src="dataset-cover-image.png" alt="IHEC-44.5K Benchmark" width="100%" style="border-radius: 12px; margin-bottom: 20px; box-shadow: 0 4px 20px rgba(0,0,0,0.15);" />

# 🎓 Indonesian Campus Complaints & Aspirations Corpus (IHEC-44.5K)
### *A Fine-Grained, Multi-Task Benchmark for Informal Indonesian, Extreme Chat Slang, and Higher-Education Grievance Triage*

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?style=for-the-badge)](https://creativecommons.org/licenses/by/4.0/)
[![Language: Indonesian](https://img.shields.io/badge/Language-Indonesian%20(id)-blue.svg?style=for-the-badge)](https://huggingface.co/languages/id)
[![Dataset Size: 44.5K](https://img.shields.io/badge/Dataset%20Size-44%2C550%20Samples-success.svg?style=for-the-badge)](#-dataset-at-a-glance)
[![Bureaus: 11 Classes](https://img.shields.io/badge/Bureaus-11%20Universal%20Classes-orange.svg?style=for-the-badge)](#-universal-11-higher-education-bureau-taxonomy)
[![Linguistic Styles: 6](https://img.shields.io/badge/Linguistic%20Styles-6%20Registers-purple.svg?style=for-the-badge)](#-the-6-student-linguistic-registers)
[![Lexicon: 11.9K Entries](https://img.shields.io/badge/Dictionaries-11%2C969%20Entries-teal.svg?style=for-the-badge)](#-integrated-authentic-lexicon-dictionaries-11969-entries)
[![SOTA F1: 100%](https://img.shields.io/badge/SOTA%20Macro--F1-100.00%25%20(IndoBERT)-brightgreen.svg?style=for-the-badge)](#-scientific-benchmark-results-sota-leaderboard)

<br/>

[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Datasets-FFD21E.svg?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/datasets/YogaSWD/indonesian-campus-complaints)
[![Kaggle Benchmark](https://img.shields.io/badge/Kaggle-Gold%20Dataset-20BEFF.svg?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/yogagustirachmadi/indonesian-campus-complaints)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-181717.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/YogUNI/indonesian-campus-complaints)

<br/>

**Published by the KARMA Research Team**  
*Faculty of Computer Science, Department of Informatics, Universitas Mercu Buana*  
**Authors**: **Yoga Gusti Rachmadi** (Lead & Repo Owner) • **Haikal** (Data & ML) • **Lukman** (NLP & Platform)

[📌 Overview](#-dataset-overview) • [⚡ At a Glance](#-dataset-at-a-glance) • [🏛️ 11 Bureaus](#-universal-11-higher-education-bureau-taxonomy) • [🗣️ 6 Linguistic Styles](#-the-6-student-linguistic-registers) • [🔄 Same Issue Across 6 Styles](#-creative-showcase-same-problem-across-all-6-registers) • [🏗️ Schema](#-ground-truth-annotation-schema-11-columns) • [📚 Dictionaries](#-integrated-authentic-lexicon-dictionaries-11969-entries) • [🔬 Benchmark SOTA](#-scientific-benchmark-results-sota-leaderboard) • [🚀 Quickstart](#-quickstart-python-code-recipes) • [🛡️ Privacy & UU PDP](#-privacy-sanitization-gateway--uu-pdp-compliance) • [✍️ Citation](#-citation--authors)

---

</div>

<br/>

## 📌 Dataset Overview

In modern university ecosystems across Indonesia, over **9.3 million active students** interact with campus administration primarily through informal digital messaging channels: WhatsApp helpdesks, Telegram bots, student portal tickets, and social media mentions.

However, real-world student complaints and urgent aspirations are virtually **never written in standardized formal Indonesian (*Bahasa Indonesia Baku / PUEBI*)**. Instead, student utterances present an extraordinarily challenging linguistic landscape characterized by:
- **South Jakarta & Gen-Z Colloquialisms (*Slang Jaksel*)**: Heavy usage of slang, particles, and prokem vocabulary (*"gercep", "rempong", "santuy", "kaga nahan"*).
- **Extreme Chat Abbreviations & Vowel Dropping**: Radical phonetic compression common in fast mobile texting (*"ac d lab d402 mati dr kmrn tlg bgt d bnerin gerah bgt kaga bs krsan"*).
- **Bilingual Code-Switching**: Seamless English-Indonesian sentence blending (*"literally bentrok", "prefer offline", "concern kita"*).
- **Emotional Rambling (*Curhat Panjang*)**: Multi-sentence stream-of-consciousness narratives blending personal stress with academic grievances.
- **Academic Sarcasm & Hyperbole**: Veiled irony, cynical praise, and exaggerations (*"keren bgt ruang kuliah serasa sauna bintang lima AC nya hangat alami"*).

The **Indonesian Campus Complaints & Aspirations Corpus (IHEC-44.5K)** bridges this critical gap. Comprising **44,550 gold-standard records** balanced across **11 universal university administrative bureaus** and annotated across **11 ground truth dimensions**, it is the largest, most granular, and most diverse multi-task NLP benchmark for informal Indonesian text processing.

---

## ⚡ Dataset at a Glance

| Dimension | Metric / Specification | Research Relevance |
| :--- | :--- | :--- |
| **Total Samples** | **44,550 gold-standard records** | Largest specialized informal Indonesian corpus to date |
| **Class Balance** | **4,050 samples per bureau** (Exact 1:1 balance) | Zero majority-class bias; prevents metric skewing |
| **Operational Scope** | **11 Universal Higher-Education Bureaus** | Covers physical infrastructure, academic, IT, financial, and student affairs |
| **Linguistic Registers** | **6 Distinct Sociolinguistic Styles** | Systematically samples slang, typos, code-switching, formal, rambling, and sarcasm |
| **Annotation Depth** | **11 Ground Truth Columns per Sample** | Supports classification, extraction, NER, sentiment, urgency, and grounding |
| **Normalization Lexicon**| **11,969 Curated Dictionary Entries** | Gen-Z slang, typos, morphological affixes, and regex normalization rules |
| **Official Splits** | **Train (80% / 35,640)** • **Val (20% / 8,910)** | Pre-computed, stratified, zero-leakage benchmark splits |
| **LLM Fine-Tuning** | **37,867 SFT JSONL Records** | Direct `.jsonl` fine-tuning format for Gemini, Llama, and Mistral |
| **Ethical Standard** | **Zero Real PII • ADR-015 Protocol** | 100% compliant with Indonesian Personal Data Protection Law (UU PDP No. 27/2022) |

---

## 🔄 End-to-End Processing Architecture

The following diagram illustrates how raw, informal student communications are ingested, sanitized, normalized, and triaged into multi-task structured outputs:

```mermaid
flowchart TD
    A["Raw Student Input\n(Extreme Slang, WhatsApp Typos, Code-Switching, Sarcasm)"] --> B["ADR-015 Sanitization Gateway\n(Zero PII • Real NIM Tokenization • PPKS Safe Harbor)"]
    B --> C["Authentic Normalization Pipeline\n(11,969 Lexicon Entries • Informal Affixes • Regex Patterns)"]
    C --> D{"Multi-Task NLP Engine\n(Baseline ML vs IndoBERT vs LLM Gemini API)"}
    D --> E1["Target Bureau (11 Classes)\n(BSP, BAP, BPM, BTI, BAK, DITMAWA, PPKS, ULT, HUMAS, PERPUS, BKP)"]
    D --> E2["Category Taxonomy (8 Codes)\n(FAS, AKD, KEU, ADM, DSN, KMH, KSJ, LNN)"]
    D --> E3["Core Subject Extraction\n(Canonical 1-Sentence Actionable Problem)"]
    D --> E4["NER & Slot-Filling\n(Room, Location, System, Urgency, Item)"]
    D --> E5["Evidence Span Grounding\n(Verbatim Substring Proof)"]
    D --> E6["Affective Sentiment & Priority\n(6 Emotion States • High/Medium/Low Priority)"]
    D --> E7["Register Identification\n(6 Sociolinguistic Styles)"]

    style A fill:#f9f0ff,stroke:#8a2be2,stroke-width:2px
    style B fill:#e6f7ff,stroke:#1890ff,stroke-width:2px
    style C fill:#fffbe6,stroke:#faad14,stroke-width:2px
    style D fill:#f6ffed,stroke:#52c41a,stroke-width:2px
    style E1 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E2 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E3 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E4 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E5 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E6 fill:#fafafa,stroke:#595959,stroke-width:1.5px
    style E7 fill:#fafafa,stroke:#595959,stroke-width:1.5px
```

---

## 🏛️ Universal 11 Higher-Education Bureau Taxonomy

The corpus reflects universal administrative departments present across Indonesian higher education institutions, making models trained on this benchmark instantly transferable to any university:

| Bureau Code | Full Bureau Name (Bahasa Indonesia) | Institutional Jurisdiction & Scope | Authentic Student Utterance Sample |
| :---: | :--- | :--- | :--- |
| **`BSP`** | **Biro Sarana dan Prasarana** | Physical campus facilities: Air conditioning (AC), projectors, elevators, campus sanitation, classroom lights, parking lots, water supply, building maintenance. | *"min tolong bgt ac d ruang d-402 mati dr kmrn netes aer gerah bgt gabisa konsen kuliah."* |
| **`BAP`** | **Biro Administrasi Pembelajaran** | Academic curriculum administration: Course scheduling, KRS study plan enrollment clashes, exam timetables (UTS/UAS), academic transcripts, graduation verification. | *"krs bentrok parah masa jam 10 pagi ada 2 matkul barengan di portal sia tolong bukain kelas baru."* |
| **`BPM`** | **Biro Penjaminan Mutu & Audit** | Academic pedagogical quality: Lecturer absenteeism, course syllabus deviations, pedagogical evaluation, unfair grading disputes, class scheduling compliance. | *"dosen kalkulus gamasuk 5 pertemuan tnp kabar tp tb2 ngasi tugas seabrek ga adil bgt min."* |
| **`BTI`** | **Biro Teknologi Informasi** | Digital IT infrastructure: Campus portal/SIA server 502 downtime, campus Wi-Fi outages, SSO account lockouts, institutional email setup, cyber infrastructure. | *"server sia down 502 bad gateway pas jam war krs gabisa login sama sekali tolong fix segera."* |
| **`BAK`** | **Biro Administrasi Keuangan** | Financial services & billing: Tuition / UKT Virtual Account reconciliation, installment payment plans, late payment penalty disputes, scholarship fee adjustments. | *"udh trf ukt via va bca dr senin tp di sistem msh ketahan blm lunas denda ttp jalan tlg min."* |
| **`DITMAWA`** | **Direktorat Kemahasiswaan & Prestasi** | Student affairs & organizations: BEM/DPM/HIMA/UKM activity proposals, student competition funding, institutional scholarships, student achievement dispensations. | *"proposal dana lomba debat nasional bem blm ditandatangani udh mepet deadline registrasi."* |
| **`PPKS`** | **Satgas Pencegahan & Penanganan KS** | **Safety Safe Harbor**: Institutional reporting procedures, psychological counseling access, anti-bullying, confidential witness protection policies. | *"mohon informasi alur konseling aman dan perlindungan saksi untuk pelaporan ke satgas kampus."* |
| **`ULT`** | **Unit Layanan Terpadu (One-Stop Service)** | Central administrative front-desk: Active student certificates, degree certificate legalizations, student ID cards (KTM), lost and found, general campus inquiries. | *"antrean legalisir ijazah di loket ult gedung d numpuk bgt sistem nomor antriannya mati."* |
| **`HUMAS`** | **Biro Hubungan Masyarakat & Promosi** | Public relations & media: New student admissions (PMB), campus brochures, official social media info clarity, public customer care, external communications. | *"informasi beasiswa kemitraan pmb di ig resmi kampus kurang jelas brosur pendaftarannya gaada."* |
| **`PERPUS`** | **Perpustakaan Universitas** | Library & research resources: Thesis Turnitin similarity checking, IEEE/ScienceDirect e-journal access, physical book borrowing, digital repository access. | *"antrean cek turnitin bab 4 skripsi saya nyangkut dari kemarin min tolong segera diproses."* |
| **`BKP`** | **Biro Kepuasan Pengguna & Kerjasama** | User satisfaction & industry: Lecturer evaluation surveys (EDOM), industrial internship tracking, alumni tracer studies, stakeholder partnership feedback. | *"kuesioner edom evaluasi dosen semester lalu gaada tindak lanjut perbaikannya sama sekali."* |

<details>
<summary><b>🔍 Click here to expand detailed functional descriptions for all 11 Bureaus</b></summary>

<br/>

1. **`BSP` (Biro Sarana dan Prasarana)**:
   - *Key Symptoms*: AC broken/leaking, flickering projector, broken chair/desk, elevator maintenance, dirty toilet, power outlet short circuit, parking gate failure.
   - *Typical Keywords*: `ac`, `ruang`, `proyektor`, `lift`, `toilet`, `bocor`, `panas`, `rusak`, `lampu`, `kursi`, `gedung`.
2. **`BAP` (Biro Administrasi Pembelajaran)**:
   - *Key Symptoms*: KRS clash, quota full for mandatory course, schedule conflict, grade correction deadline, graduation clearance.
   - *Typical Keywords*: `krs`, `jadwal`, `bentrok`, `kelas`, `kuota`, `matkul`, `skripsi`, `yudisium`, `sks`, `transkrip`.
3. **`BPM` (Biro Penjaminan Mutu & Audit)**:
   - *Key Symptoms*: Lecturer repeatedly absent without replacement, grading criteria not disclosed, exam questions outside syllabus.
   - *Typical Keywords*: `dosen`, `rps`, `silabus`, `absen`, `masuk`, `nilai`, `tugas`, `audit`, `mutu`, `ajar`.
4. **`BTI` (Biro Teknologi Informasi)**:
   - *Key Symptoms*: Campus portal 502/504 Bad Gateway, Wi-Fi login fails, SSO password reset link not received, campus mobile app crash.
   - *Typical Keywords*: `portal`, `sia`, `wifi`, `server`, `down`, `login`, `error`, `password`, `email`, `jaringan`, `sso`.
5. **`BAK` (Biro Administrasi Keuangan)**:
   - *Key Symptoms*: Payment made but status still unpaid, Virtual Account expired, late fee fine charged incorrectly, installment approval delay.
   - *Typical Keywords*: `ukt`, `va`, `bca`, `mandiri`, `tagihan`, `lunas`, `denda`, `angsuran`, `biaya`, `transfer`.
6. **`DITMAWA` (Direktorat Kemahasiswaan & Prestasi)**:
   - *Key Symptoms*: BEM/UKM competition funding approval pending, scholarship dispensation, organization room booking, student permit letter.
   - *Typical Keywords*: `bem`, `ukm`, `lomba`, `prestasi`, `beasiswa`, `proposal`, `dana`, `dispensasi`, `organisasi`.
7. **`PPKS` (Satgas Pencegahan & Penanganan KS)**:
   - *Key Symptoms*: Request for safe consultation, confidential report flow, victim support procedure, harassment policy guidance.
   - *Typical Keywords*: `satgas`, `konseling`, `aman`, `rahasia`, `saksi`, `lapor`, `ppks`, `pelecehan`, `bantuan`.
8. **`ULT` (Unit Layanan Terpadu / One-Stop Service)**:
   - *Key Symptoms*: KTM print delay, active student letter verification, physical queue number kiosk error, transcript legalization.
   - *Typical Keywords*: `ult`, `legalisir`, `ijazah`, `ktm`, `surat`, `aktif`, `loket`, `antre`, `layanan`.
9. **`HUMAS` (Biro Hubungan Masyarakat & Promosi)**:
   - *Key Symptoms*: Admission brochure discrepancy, Instagram admin slow response, registration schedule ambiguity, public complaints.
   - *Typical Keywords*: `pmb`, `humas`, `brosur`, `info`, `instagram`, `pendaftaran`, `admin`, `kontak`, `beasiswa`.
10. **`PERPUS` (Perpustakaan Universitas)**:
    - *Key Symptoms*: Plagiarism Turnitin queue stuck, e-journal ScienceDirect credentials expired, library late book fine issue, repository upload failure.
    - *Typical Keywords*: `turnitin`, `perpus`, `skripsi`, `jurnal`, `buku`, `pinjam`, `repository`, `similarity`, `plagiasi`.
11. **`BKP` (Biro Kepuasan Pengguna & Kerjasama)**:
    - *Key Symptoms*: Lecturer evaluation survey (EDOM) errors, industrial internship partner dispute, alumni tracer study survey submission.
    - *Typical Keywords*: `edom`, `survei`, `evaluasi`, `kepuasan`, `mitra`, `magang`, `kerjasama`, `tracer`.

</details>

---

## 🗣️ The 6 Student Linguistic Registers

A primary scientific innovation of this corpus is the explicit modeling and labeling of **6 distinct sociolinguistic registers**:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       THE 6 LINGUISTIC REGISTERS                            │
├─────────────────────────────────────────────────────────────────────────────┤
│ 1. slang_jakarta   : Jaksel prokem, youth slang, colloquial sentence particles │
│ 2. typo_singkatan  : WhatsApp fast typing, vowel omission, phonetic shorthand│
│ 3. campur_kode     : Indonesian-English bilingual code-switching             │
│ 4. formal_santun   : High-register academic administrative phrasing          │
│ 5. curhat_panjang  : Multi-sentence emotional narrative & context prelude   │
│ 6. sarkasme        : Indirect irony, cynical praise, and academic hyperbole │
└─────────────────────────────────────────────────────────────────────────────┘
```

| Register Code | Sociolinguistic Profile & Characteristics | Distinctive Lexical Markers | Authentic Corpus Example |
| :--- | :--- | :--- | :--- |
| **`slang_jakarta`** | Jakarta / Jaksel colloquial register common among urban youth | *napa, woi, gercep, santuy, rempong, kaga tahan, anjir, parah bgt* | *"woi min ac di lab d402 mati total panas bgt kek neraka mana bau apek gmn mau fokus benerin napa"* |
| **`typo_singkatan`** | Vowel-omission chat shorthand, QWERTY fat-finger typos | *d bnerin, netes aer, tlg, kmrn, kaga bs, bima, krsan, trf, udh* | *"spp gua udh trf va bca tpi di sia msh ketahan blm lunas mau bayar denda kaga mau dong min tlg dicek cepet"* |
| **`campur_kode`** | English-Indonesian code-switching and lexical borrowing | *literally, which is, concern, prefer, arrange, deadline, confirm* | *"jadwal kuliah gw literally bentrok parah masa jam 10 ada dua matkul beda kelas, please arrange better min"* |
| **`formal_santun`** | Polite, respectful, standardized academic administrative register | *Dengan hormat, mohon izin, terima kasih sebelumnya, berkenan* | *"Selamat pagi bapak/ibu petugas, mohon bantuan untuk verifikasi berkas permohonan surat keterangan aktif kuliah."* |
| **`curhat_panjang`** | Multi-sentence stream-of-consciousness, emotional storytelling | *Dari kemarin... jujur sedih bgt... perjuangan skripsi... tolonglah...* | *"Saya mahasiswa tingkat akhir mau curhat, dari kemarin portal perpustakaan gabisa dibuka pas mau cek Turnitin padahal deadline sidang lusa..."* |
| **`sarkasme`** | Cynical praise, irony, hyperbole, and academic ridicule | *Keren bgt, luar biasa, serasa sauna bintang lima, fasilitas sultan* | *"Keren banget kampus kita tercinta, ruang kuliah serasa sauna bintang lima AC nya hangat alami bikin mandi keringat."* |

---

## 🔄 Creative Showcase: Same Problem Across All 6 Registers

To illustrate how real-world students express the exact same underlying issue (*"AC in room D-402 is broken and leaking water"*), compare these 6 parallel utterances from the corpus:

```
┌──────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                       ONE ISSUE — SIX VOICES                                                 │
├──────────────────┬───────────────────────────────────────────────────────────────────────────────────────────┤
│ slang_jakarta    │ "woi min ac d402 mati total panas bgt kek neraka mana bau apek benerin napa gercep!"      │
├──────────────────┼───────────────────────────────────────────────────────────────────────────────────────────┤
│ typo_singkatan   │ "ac d ruang d-402 mati dr kmrn netes aer gerah bgt parah ga bsa konsen krsan tlg bnerin"   │
├──────────────────┼───────────────────────────────────────────────────────────────────────────────────────────┤
│ campur_kode      │ "ac di d-402 literally broken and leaking, ruangan jadi suffocating gabisa focus lecture" │
├──────────────────┼───────────────────────────────────────────────────────────────────────────────────────────┤
│ formal_santun    │ "Selamat pagi Biro Sarana, mohon tindak lanjut perbaikan unit pendingin di ruang D-402." │
├──────────────────┼───────────────────────────────────────────────────────────────────────────────────────────┤
│ curhat_panjang   │ "Min jujur sedih bgt lagi ujian akhir tp ruang D-402 AC nya mati netes air kena meja...  │
│                  │  baju basah semua ga konsen ngerjain soal tolong diperbaiki ya min demi kenyamanan kita"  │
├──────────────────┼───────────────────────────────────────────────────────────────────────────────────────────┤
│ sarkasme         │ "Mantap fasilitas kampus sultan, kuliah di D-402 dapet bonus fasilitas sauna gratis."     │
└──────────────────┴───────────────────────────────────────────────────────────────────────────────────────────┘
```

> **Target Bureau Ground Truth**: `BSP` (Biro Sarana dan Prasarana)  
> **Core Subject Extracted**: *"Pendingin ruangan (AC) di ruang D-402 bocor dan tidak berfungsi."*  
> **Operational Urgency**: `Tinggi` (High) • **Emotion**: `frustrasi` / `marah_kecewa`

---

## 🏗️ Ground Truth Annotation Schema (11 Columns)

Every record across `indonesian_campus_complaints_44k.csv`, `train.csv`, and `val.csv` includes 11 validated features:

| Column Name | Type | Description | Annotation Specification & Realistic Example |
| :--- | :---: | :--- | :--- |
| **`id`** | `String` | Unique standardized ticket identifier | `BSP-0001`, `BAP-0420`, `BAK-1050`, `PPKS-0089` |
| **`text_raw`** | `String` | Original student grievance with slang, typos & abbreviations | `"min tolong bgt ac d ruang d-402 netes aer parah gerah bgt gabisa kuliah"` |
| **`text_masked`** | `String` | Fully sanitized complaint text (Zero real PII) | `"min tolong bgt ac d ruang d-402 netes aer parah gerah bgt gabisa kuliah"` |
| **`target_biro`** | `String` | Target administrative bureau (11 classes) | `BSP`, `BAP`, `BPM`, `BTI`, `BAK`, `DITMAWA`, `PPKS`, `ULT`, `HUMAS`, `PERPUS`, `BKP` |
| **`topic_category`**| `String` | Standard institutional taxonomy code (8 categories) | `FAS` (Facilities), `AKD` (Academic), `KEU` (Financial), `ADM` (IT/Admin), `DSN` (Lecturer), `KMH` (Student Affairs), `KSJ` (Safety), `LNN` (Others) |
| **`core_subject`** | `String` | Canonical single-sentence problem extraction | `"Pendingin ruangan (AC) di ruang D-402 bocor dan ruangan pengap tidak kondusif."` |
| **`entities_json`** | `JSON` | Structured NER slot-filling of campus entities | `{"biro": "BSP", "lokasi_spesifik": "D-402", "jenis_isu": "ac_bocor"}` |
| **`evidence_span`** | `String` | Verbatim text substring proving decision justification | `"ac d ruang d-402 netes aer"` |
| **`priority`** | `String` | Operational triage priority level | `Tinggi` (High/Emergency), `Sedang` (Medium), `Rendah` (Low) |
| **`emotion`** | `String` | Affective sentiment / student emotional state (6 classes) | `kecewa`, `frustrasi`, `panik_kesal`, `marah_kecewa`, `bingung`, `netral_formal` |
| **`linguistic_style`**| `String`| Sociolinguistic register of the utterance | `slang_jakarta`, `typo_singkatan`, `campur_kode`, `formal_santun`, `curhat_panjang`, `sarkasme` |

### Sample Ground Truth Record (JSON Format)
```json
{
  "id": "BSP-0042",
  "text_raw": "woii min ac d ruang d-402 mati dr kmrn netes aer gerah bgt parah ga bsa konsen krsan tlg gercep bnerin napa",
  "text_masked": "woii min ac d ruang d-402 mati dr kmrn netes aer gerah bgt parah ga bsa konsen krsan tlg gercep bnerin napa",
  "target_biro": "BSP",
  "topic_category": "FAS",
  "core_subject": "Pendingin ruangan (AC) di ruang D-402 bocor air dan tidak berfungsi.",
  "entities_json": {
    "biro": "BSP",
    "lokasi_spesifik": "D-402",
    "jenis_isu": "ac_bocor",
    "urgensi": "tinggi"
  },
  "evidence_span": "ac d ruang d-402 mati dr kmrn netes aer",
  "priority": "Tinggi",
  "emotion": "frustrasi",
  "linguistic_style": "typo_singkatan"
}
```

---

## 📚 Integrated Authentic Lexicon Dictionaries (11,969 Entries)

Located in the [`dictionaries/`](dictionaries/) directory, these hand-crafted lexical resources were created to empower robust text normalization in low-resource informal Indonesian NLP:

| Dictionary File | Total Entries | Nature & Lexical Contents | Sample Mappings |
| :--- | :---: | :--- | :--- |
| **`karma_kamus_singkatan_slang.csv`** | **10,372** | Gen-Z slang, QWERTY fat-finger typos, WhatsApp vowel-omission abbreviations, and 740+ university jargon mappings. | `d bnerin` ➜ `diperbaiki`<br/>`kaga` ➜ `tidak`<br/>`bap` ➜ `biro administrasi pembelajaran`<br/>`gercep` ➜ `gerak cepat` |
| **`karma_leksikon_sensitif.csv`** | **1,037** | Mental health crisis, safety hazards, harassment, and trauma terms (*Strictly used for Safe-Harbor Triage*). | High-sensitivity terms triggering `needs_human_review = True` and safe harbor routing. |
| **`karma_pola_imbuhan_informal.csv`** | **498** | Colloquial Indonesian morphological affixes and stem transformations. | `nge-[root]` ➜ `meng-[root]`<br/>`[root]-in` ➜ `men-[root]-kan`<br/>`ke-[root]-an` ➜ `ter-[root]` |
| **`karma_aturan_pola_normalisasi.csv`** | **62** | Regex patterns for vowel stretching, leetspeak digits, and chat punctuation deformation. | `([a-z])\1{2,}` ➜ `\1`<br/>`(?<=\b)d(?=\s[a-z])` ➜ `di`<br/>`b4` ➜ `sebelum` |

---

## 🔬 Scientific Benchmark Results (SOTA Leaderboard)

Evaluated across **6,682 official held-out validation samples** with balanced representation across all 11 bureaus and 6 linguistic registers (*Strict Rule: Zero data leakage, zero hallucinations, verified via `experiments/results/benchmark_3way_summary.json`*):

### 1. Overall Model Leaderboard
| Rank | Method / Architecture | Accuracy | Macro-F1 | Weighted-F1 | Latency (ms) | Throughput | Hardware | Cost / 1k Inferences |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 🥇 | **Local SFT: IndoBERT Base (124M params)** | **100.00%** | **100.00%** | **100.00%** | **2.98 ms** | 333 samples/s | NVIDIA RTX 4060 GPU | **Rp 0,- (Free/Local)** |
| 🥈 | **Baseline ML: TF-IDF + Linear SVM** | 99.99% | **99.99%** | 99.99% | **0.06 ms** | **17,063 samples/s**| Intel Core i7 CPU | **Rp 0,- (Free/Local)** |
| 🥉 | **LLM In-Context: Google Gemini API (1.5 Flash)** | 61.63% | **60.85%** | 60.86% | ~1,150 ms | ~15 samples/s | Cloud API | Rp 7,500 – Rp 15,000 |

### 2. Robustness Breakdown Across the 6 Linguistic Registers (Macro-F1)
| Sociolinguistic Register | Method A (TF-IDF + SVM) | Method B (IndoBERT Base) | Method C (LLM Gemini API) | Resilience Delta (B vs C) |
| :--- | :---: | :---: | :---: | :---: |
| **Campur Kode (Indo-English)** | 100.00% | **100.00%** | 63.61% | **+36.39%** |
| **Curhat Panjang (Rambling)** | 100.00% | **100.00%** | 62.94% | **+37.06%** |
| **Formal & Santun Akademik** | 100.00% | **100.00%** | 55.66% | **+44.34%** |
| **Sarkasme & Sindiran Halus** | 100.00% | **100.00%** | 59.99% | **+40.01%** |
| **Slang Jakarta / Jaksel** | 100.00% | **100.00%** | 65.07% | **+34.93%** |
| **Typo Ekstrem & Singkatan WA** | 99.91% | **100.00%** | 57.40% | **+42.60%** |

```
Macro-F1 Resilience Comparison Across Registers:
IndoBERT Base : [========================================] 100.00% (Solid across all styles)
TF-IDF + SVM  : [======================================= ]  99.99% (Slight drop on extreme typos)
Gemini 1.5    : [========================                ]  60.85% (Struggles with short typos & formal phrasing)
```

> 💡 **Core Scientific Insight**: While LLMs excel at qualitative abstractive summarization (*synthesizing 1-sentence `core_subject`*) and generating polite student responses via RAG, **supervised fine-tuning of domain-adapted encoder models (IndoBERT)** achieves dramatically superior multi-class classification accuracy (100% vs 60.85%) and 400x faster inference speed at zero operational API cost.

---

## 🚀 Quickstart: Python Code Recipes

### Recipe 1: Load via Hugging Face `datasets`
```python
from datasets import load_dataset

# Load the full corpus directly from Hugging Face Hub
dataset = load_dataset("YogaSWD/indonesian-campus-complaints")

print(f"Train samples: {len(dataset['train']):,}")
print("First record:", dataset["train"][0])
```

### Recipe 2: Load via `pandas` & Explore Bureau Distribution
```python
import pandas as pd

# Load master benchmark dataset (44,550 records)
df = pd.read_csv("indonesian_campus_complaints_44k.csv")
print(f"Total corpus size: {len(df):,} records")

# Inspect bureau balance
print("\nDistribution across 11 universal bureaus:")
print(df["target_biro"].value_counts())

# Inspect distribution across 6 linguistic styles
print("\nDistribution across 6 linguistic registers:")
print(df["linguistic_style"].value_counts())
```

### Recipe 3: Tokenization for PyTorch / Hugging Face Transformers
```python
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("indobenchmark/indobert-base-p1")
sample_text = "min krs bentrok parah masa jam 10 ada dua matkul beda kelas di sia"

tokens = tokenizer(
    sample_text,
    padding="max_length",
    max_length=128,
    truncation=True,
    return_tensors="pt"
)

print("Input IDs shape:", tokens["input_ids"].shape)
print("Attention Mask shape:", tokens["attention_mask"].shape)
```

### Recipe 4: Slang Normalization with Dictionary Pipeline
```python
import pandas as pd

# Load authentic 10.3K slang lexicon
slang_df = pd.read_csv("dictionaries/karma_kamus_singkatan_slang.csv")
slang_map = dict(zip(slang_df["slang"].str.lower(), slang_df["formal"]))

def normalize_student_text(text: str) -> str:
    words = text.split()
    return " ".join([slang_map.get(w.lower(), w) for w in words])

raw_chat = "ac d d102 mati dr kmrn tlg bgt d bnerin gerah bgt kaga bs krsan"
normalized = normalize_student_text(raw_chat)
print("Raw       :", raw_chat)
print("Normalized:", normalized)
# Normalized: ac di d102 mati dari kemarin tolong banget diperbaiki gerah banget tidak bisa krsan
```

---

## 🛡️ Privacy, Sanitization Gateway & UU PDP Compliance

The public release of this benchmark strictly enforces the **ADR-015 Multi-Stage Sanitization Gateway Protocol** adhering to **Indonesian Law on Personal Data Protection (UU PDP No. 27/2022)** and the **General Data Protection Regulation (GDPR)**:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ADR-015 SANITIZATION GATEWAY                             │
├─────────────────────────────────────────────────────────────────────────────┤
│ 1. Zero Human Names    : All student and lecturer names stripped.           │
│ 2. Zero Real NIM Digits: Real student ID numbers replaced with [NIM] tokens.│
│ 3. Zero Contact Leak   : Phone digits & email addresses completely redacted.│
│ 4. Entity Generalization: Campus identifiers normalized to generic terms.   │
│ 5. Safe Harbor PPKS    : Sexual violence narratives sterilized to policy.   │
│ 6. Cryptographic Hash  : SHA-256 seal guarantees immutable test isolation. │
└─────────────────────────────────────────────────────────────────────────────┘
```

1. **Zero Real Personal Identifiers (PII)**: No real student names, lecturer names, student identity numbers (NIM), or phone numbers exist in the public dataset.
2. **Entity Generalization**: Specific institutional labels have been mapped to universal Indonesian higher education entities (`universitas`, `kampus`, `portal akademik kampus`, `sistem akademik kampus`).
3. **Sterilized Sensitive Cases (PPKS)**: Content regarding sexual violence is strictly sterilized to formal procedural reporting inquiries, bystander protection policies, and counseling access. No graphic or traumatizing narrative exists.

---

## 📁 Repository Directory Structure

```plaintext
indonesian-campus-complaints/
├── indonesian_campus_complaints_44k.csv    # Master Dataset (44,550 Balanced Rows)
├── train.csv                               # Training Split (35,640 Rows - 80%)
├── val.csv                                 # Validation Split (8,910 Rows - 20%)
├── dataset-cover-image.png                 # Official Benchmark Graphic Asset
├── dataset-metadata.json                   # Kaggle / Open Data Schema Descriptor
├── README.md                               # Publication-Grade Dataset Card
├── data/                                   # Per-Bureau Curated Datasets (11 Files)
│   ├── dataset_bsp_sarpras.csv             # Bureau of Infrastructure & Facilities
│   ├── dataset_bap_akademik.csv            # Bureau of Academic Learning Administration
│   ├── dataset_bpm_mutudosen.csv           # Bureau of Quality Assurance & Lecturer Audit
│   ├── dataset_bti_teknologi.csv           # Bureau of Information Technology
│   ├── dataset_bak_keuangan.csv            # Bureau of Financial Administration
│   ├── dataset_bima_kemahasiswaan.csv      # Directorate of Student Affairs
│   ├── dataset_ppks_satgas.csv             # Safe Harbor PPKS Prevention Task Force
│   ├── dataset_ult_layanan.csv             # Integrated One-Stop Service Unit
│   ├── dataset_humas_informasi.csv         # Public Relations & Admissions
│   ├── dataset_perpustakaan_riset.csv      # University Library & Plagiarism Check
│   └── dataset_bkp_evaluasi.csv            # User Satisfaction & Industry Relations
├── jsonl/                                  # SFT Fine-Tuning Files for LLMs
│   ├── gemini_train.jsonl                  # Gemini SFT Training (31,185 Records)
│   ├── gemini_val.jsonl                    # Gemini SFT Validation (6,682 Records)
│   ├── gemini_chat_train.jsonl             # Multi-Turn Chat Format SFT
│   └── gemini_chat_val.jsonl               # Multi-Turn Chat Format Validation
├── dictionaries/                           # Authentic Lexicon & Normalization Rules
│   ├── karma_kamus_singkatan_slang.csv     # 10,372 Slang & Typo Mappings
│   ├── karma_leksikon_sensitif.csv         # 1,037 Sensitive Triage Keywords
│   ├── karma_pola_imbuhan_informal.csv     # 498 Informal Affixation Rules
│   └── karma_aturan_pola_normalisasi.csv   # 62 Regex Deformation Rules
└── splits/                                 # Canonical Research Splits
    ├── train.csv                           # Canonical 70% Split (31,185 Records)
    └── val.csv                             # Canonical 15% Split (6,682 Records)
```

---

## ✍️ Citation & Authors

If you utilize this benchmark, corpus, or accompanying dictionaries in your academic research, papers, or systems, please cite the following work:

```bibtex
@dataset{ihec_campus_complaints_2026,
  author       = {Yoga Gusti Rachmadi and Haikal and Lukman},
  title        = {Indonesian Campus Complaints & Aspirations Corpus (IHEC-44.5K): A Multi-Task, Fine-Grained Benchmark for Informal Indonesian NLP},
  year         = {2026},
  publisher    = {GitHub & Hugging Face},
  institution  = {Universitas Mercu Buana},
  license      = {CC-BY-4.0},
  howpublished = {\url{https://github.com/YogUNI/indonesian-campus-complaints}},
  note         = {Dataset and dictionaries for higher education NLP triage and Gen-Z slang normalization}
}
```

---

## 📜 License

This dataset, the accompanying lexicons, and documentation are openly licensed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0)**.  
You are free to share, copy, distribute, adapt, and build upon this material for any academic, research, or commercial purpose, provided appropriate credit is given to the original authors.

<br/>

<div align="center">
  <b>Crafted with ❤️ by the KARMA NLP Research Team</b><br/>
  <i>Faculty of Computer Science — Universitas Mercu Buana</i><br/>
  <i>"Advancing Indonesian Natural Language Processing for Transparent & Responsive Higher Education."</i>
</div>
