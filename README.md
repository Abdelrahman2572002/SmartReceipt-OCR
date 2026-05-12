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
