# DIA-HARM: Dialectal Disparities in Harmful Content Detection Across 50 English Dialects

<p align="center">
  <a href="https://arxiv.org/abs/2604.05318"><strong>arXiv Paper</strong></a> &nbsp;|&nbsp;
  <a href="https://arxiv.org/pdf/2604.05318"><strong>PDF</strong></a> &nbsp;|&nbsp;
  <a href="https://jsl5710.github.io/dia-harm/"><strong>Project Page</strong></a> &nbsp;|&nbsp;
  <a href="https://github.com/jsl5710/dia-harm"><strong>Code &amp; Data</strong></a>
</p>

**Jason Lucas**<sup>1</sup>, **Matt Murtagh**<sup>*3</sup>, **Ali Al-Lawati**<sup>*1</sup>, **Uchendu Uchendu**<sup>1</sup>, **Adaku Uchendu**<sup>2</sup>, **Dongwon Lee**<sup>1</sup>

<sup>1</sup>The Pennsylvania State University &nbsp; <sup>2</sup>MIT Lincoln Laboratory &nbsp; <sup>3</sup>The University of Dublin

<sup>*</sup>Equal contribution as co-second author

**Accepted at ACL 2026 — Main Conference** 🎉

---

## Abstract

Harmful content detectors—particularly disinformation classifiers—are predominantly developed and evaluated on Standard American English (SAE), leaving their robustness to dialectal variation unexplored. We present **DIA-HARM**, the first benchmark for evaluating disinformation detection robustness across **50 English dialects** spanning U.S., British, African, Caribbean, and Asia-Pacific varieties. Using Multi-VALUE's linguistically grounded transformations, we introduce **D3** (Dialectal Disinformation Detection), a corpus of **195K samples** derived from established disinformation benchmarks. Our evaluation of **16 detection models** reveals systematic vulnerabilities: human-written dialectal content degrades detection by **1.4–3.6% F1**, while AI-generated content remains stable. Fine-tuned transformers substantially outperform zero-shot LLMs (**96.6% vs. 78.3%** best-case F1), with some models exhibiting catastrophic failures exceeding **33% degradation** on mixed content. Cross-dialectal transfer analysis across **2,450 dialect pairs** shows that multilingual models (mDeBERTa: **97.2% average F1**) generalize effectively, while monolingual models like RoBERTa and XLM-RoBERTa fail on dialectal inputs. These findings demonstrate that current disinformation detectors may systematically disadvantage hundreds of millions of non-SAE speakers worldwide. We release the DIA-HARM framework, D3 corpus, and evaluation tools.

## Key Highlights

| Metric | Value |
|--------|-------|
| English Dialects | 50 (U.S., British, African, Caribbean, Asia-Pacific) |
| D3 Corpus Samples | 195K+ |
| Detection Models | 16 (10 fine-tuned + 5 zero-shot LLMs + 1 ICL) |
| Morphosyntactic Rules | 189 (12 grammatical categories from eWAVE) |
| Cross-Dialect Pairs | 2,450 |
| Best Avg F1 | 97.2% (mDeBERTa) |

## Repository Structure

```
dia-harm/
├── readme.md
├── f3/                  # F3 dataset splits (CSV files)
│   ├── f3_1.csv ... f3_12.csv
│   └── split_f3.py      # Script for splitting F3 data
├── fake_samples/         # Multi-dataset fake samples
│   └── multi_datasets_fake_samples.csv
└── outputs/              # Dialect-transformed outputs (50 dialects)
    ├── aboriginal_english/
    ├── appalachian_english/
    ├── colloquial_american_english/
    ├── jamaican_english/
    ├── nigerian_english/
    └── ... (50 dialect directories)
```

## Dialect Transformations

Dialectal transformations are generated using [Multi-VALUE](https://github.com/SALT-NLP/multi-value), applying **189 morphosyntactic rules** across **12 grammatical categories** derived from the electronic World Atlas of Varieties of English (eWAVE).

## Data Access

- **F3 Dataset**: [Google Drive](https://drive.google.com/file/d/1JGp4e3auFwyzAPSpIdAf1W5D6YbOFnNC/view?usp=sharing)
- **Dialect Outputs**: Available in the `outputs/` directory (50 dialect subdirectories)
- **Fake Samples**: Available in the `fake_samples/` directory

## Citation

If you use DIA-HARM in your research, please cite:

```bibtex
@inproceedings{lucas2026diaharm,
  title={DIA-HARM: Dialectal Disparities in Harmful Content Detection Across 50 English Dialects},
  author={Lucas, Jason and Murtagh, Matt and Al-Lawati, Ali and Uchendu, Uchendu and Uchendu, Adaku and Lee, Dongwon},
  booktitle={Proceedings of the 64th Annual Meeting of the Association for Computational Linguistics (ACL 2026), Main Conference},
  year={2026},
  eprint={2604.05318},
  archivePrefix={arXiv}
}
```
