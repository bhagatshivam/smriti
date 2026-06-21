# Smriti (स्मृति)

Open Sanskrit-English parallel corpus and Indian heritage NLP datasets.

> Smriti (स्मृति) — "that which is remembered." The class of remembered
> Indian scriptures, passed down through generations. This project makes
> that scholarship machine-readable, so it is never forgotten again.

**Status:** Phase 1 — building the foundation dataset (in development)
**License:** [CC BY-SA 4.0](LICENSE)
**Founder:** Shivam (https://github.com/BookWanderer))

---

## The Problem

Sanskrit is one of the oldest living languages with one of the richest
documented heritages in the world, yet the largest public Sanskrit-English
machine translation dataset contains under 400,000 sentence pairs —
a fraction of what exists for Chinese, Japanese, Korean, or Arabic.

The translations already exist. Scholars did this work over a century ago,
and the texts are public domain. The gap is an engineering and coordination
problem, not a knowledge problem. Smriti exists to close it.

## Two Datasets, One Project

| | Smriti-Parallel | Smriti-Heritage |
|---|---|---|
| **What** | Verse-aligned Sanskrit-English translation corpus | Structured English knowledge dataset on Indian mythology & history |
| **For** | MT researchers, computational linguists | RAG systems, knowledge-aware AI applications |
| **Status** | **Phase 1 — current focus** | Phase 3 — not started |

This repository currently contains **Smriti-Parallel only**.

## Phase 1 Scope

Building a verse-aligned parallel corpus across four Principal Upanishads:

| Text | Verses |
|---|---|
| Isha Upanishad | 18 |
| Kena Upanishad | 34 |
| Katha Upanishad | 119 |
| Mundaka Upanishad | 64 |
| **Total** | **~235** |

**Sources:** Sanskrit text from [GRETIL](http://gretil.sub.uni-goettingen.de/);
English translations from public-domain pre-1928 [Project Gutenberg](https://www.gutenberg.org/)
editions.

## Repository Structure

```
smriti/
├── data/
│   ├── raw/              # untouched source pulls — never hand-edited
│   │   ├── sanskrit/
│   │   └── translations/
│   └── processed/        # cleaned, aligned JSONL — the actual dataset
├── scripts/               # parsing, alignment, and validation scripts
├── docs/
│   └── sources.md         # exact source URLs and translator attribution
└── README.md
```

## Dataset Record Schema

```json
{
  "id": "IU_1_1",
  "devanagari": "Sanskrit source text in Devanagari script",
  "iast": "IAST romanized transliteration",
  "translation_primary": "Primary English translation text",
  "translation_secondary": "Second independent English translation for validation",
  "source_text": "Isha Upanishad",
  "chapter": 1,
  "verse": 1,
  "translator_primary": "Griffith, Ralph T.H., 1896",
  "translator_secondary": "Müller, Max, 1879",
  "domain": "philosophy",
  "subdomain": "Vedanta",
  "period": "early Upanishadic",
  "license": "public_domain",
  "validated": false,
  "validator": "",
  "notes": ""
}
```

## Quality Approach

- Alignment by verse number — traditional scripture numbering does the heavy lifting
- Dual-translation consistency check — agreement between two independent
  scholarly translations is strong evidence of correct alignment
- Structural and statistical validation (missing fields, verse gaps, count mismatches)
- Human spot-check validation by Sanskrit scholars before publication

## Founding Principles

1. **Open forever** — CC BY-SA 4.0. Any derivative must remain open.
2. **Accuracy over volume** — a small, verified dataset beats a large, noisy one.
3. **Attribution always** — every source, translator, and validator is named.
4. **No duplication** — Smriti extends existing datasets (Itihāsa, Mitrasamgraha), it does not rebuild them.

## Roadmap

- **Phase 1 (current):** Smriti-Parallel v0.1 — four Upanishads, ~235 verse pairs
- **Phase 2:** Community contribution pipeline, remaining Principal Upanishads
- **Phase 3:** Vedic hymns, Puranic texts, Smriti-Heritage dataset begins
- **Phase 4:** arXiv paper, formal academic/institutional collaboration

## Contributing

Not yet open for contributions — Phase 1 is a solo build to reach a stable
v0.1. Contribution guidelines will be published at the start of Phase 2.

## License

This project is licensed under [CC BY-SA 4.0](LICENSE). All derivative
datasets must remain open under the same license.
