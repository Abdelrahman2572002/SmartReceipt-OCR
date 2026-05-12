# 🧾 Receipt OCR with PaddleOCR on SROIE 2019

An end-to-end OCR evaluation pipeline on the **ICDAR 2019 SROIE** benchmark dataset,
covering text detection, text recognition, and key information extraction from scanned receipts.

## Overview

| Stage | Approach |
|---|---|
| Text Detection | PaddleOCR (DB model) with angle classifier |
| Text Recognition | PaddleOCR CRNN-based recognizer |
| Evaluation | Polygon IoU ≥ 0.5 · CER · WER |
| Key Info Extraction | Regex rules → company, date, address, total |

## Dataset

[SROIE 2019](https://rrc.cvc.uab.es/?ch=13) — ICDAR 2019 Competition on Scanned Receipt OCR
and Information Extraction.
## Quickstart (Kaggle)

1. Add the [SROIE 2019 dataset](https://www.kaggle.com/datasets/urbikn/sroie-datasetv2)
   to your Kaggle notebook.
2. Run all cells in `sroie_paddleocr_kaggle.ipynb`.
3. Results are saved to `/kaggle/working/results/`.

```python
# Install dependencies
!pip install paddlepaddle paddleocr jiwer shapely -q

# Run
from paddleocr import PaddleOCR
ocr = PaddleOCR(use_angle_cls=True, lang='en', use_gpu=False)
result = ocr.ocr('receipt.jpg', cls=True)
```

## Outputs

| File | Description |
|---|---|
| `per_image_results.csv` | Per-image TP/FP/FN/Precision/Recall/F1 |
| `summary.json` | Aggregate detection & recognition scores |
| `key_info_extraction.csv` | Extracted company/date/address/total |
| `pred_texts/` | Per-image OCR predictions in ICDAR format |
| `gt_vs_pred.png` | Ground truth vs. prediction visualization |
| `score_distributions.png` | Histogram of per-image P/R/F1 |

## Evaluation Metrics

- **Detection:** Polygon IoU-based greedy matching at threshold 0.5
- **Recognition:** Character Error Rate (CER) and Word Error Rate (WER)
  computed over concatenated image-level transcriptions

## Potential Improvements

- Enable GPU inference (`use_gpu=True`) for 5–10× speedup
- Image preprocessing: deskewing, denoising, contrast enhancement
- Fine-tune PaddleOCR on SROIE training split
- Replace regex KIE with a BERT/LayoutLM-based NER model
- Ensemble multiple OCR engines for higher recall

## Tech Stack

Python · PaddleOCR · PaddlePaddle · OpenCV · Shapely · jiwer · NumPy · Pandas · Matplotlib

