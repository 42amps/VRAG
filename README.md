# VRAG - Vision-RAG Document Retrieval Lab

VRAG is an exploratory document intelligence lab for OCR-free Vision-RAG, page-level retrieval, and multimodal PDF understanding.

The goal is to make document retrieval work on files where text-only RAG breaks down: scanned PDFs, tables, layout-heavy reports, charts, forms, and pages where meaning depends on visual structure.

## What VRAG Means

Vision-RAG retrieves and reasons over document pages as visual artifacts, not just extracted text chunks. Instead of treating OCR as the first and most important step, the pipeline can embed rendered pages and retrieve the pages most relevant to a query.

This repo currently contains an exploratory ColQwen2 / ColPali-style notebook export. It is a lab, not a finished benchmark suite.

## Why OCR-First RAG Fails

OCR-first pipelines are useful, but they often lose information that matters:

- Tables become fragmented text.
- Multi-column layouts are read in the wrong order.
- Charts and diagrams are underrepresented or ignored.
- Form labels can detach from their values.
- Scanned or low-quality PDFs introduce extraction noise before retrieval starts.

Vision-RAG keeps the page image in the loop so retrieval can use layout, visual grouping, and text appearance alongside language.

## Current Contents

- `colqwen2_vrag.ipynb` - exploratory notebook for ColQwen2-style page retrieval and generation.
- `colqwen2_vrag.py` - Python export of the notebook for easier inspection in GitHub.

## Focus Areas

- PDF page rendering and page-level retrieval.
- OCR-free or OCR-light document retrieval.
- ColPali / ColQwen-style late-interaction embeddings.
- Retrieval over tables, charts, scanned pages, and visual layouts.
- Evaluation notes for when Vision-RAG helps compared with text-only RAG.

## Local Notes

The current notebook is GPU-oriented and was originally explored in Colab. Running it locally may require:

- Python 3.10+
- PyTorch with GPU support
- `colpali-engine`
- `transformers`
- `pdf2image`
- Poppler utilities for PDF rendering

The exact environment should be documented before treating this as a reproducible pipeline.

## Roadmap

- Add an OCR-first vs Vision-RAG comparison note.
- Add a small sample PDF page retrieval pipeline.
- Add ColPali / ColQwen reading notes with links to the relevant papers and model cards.
- Separate reusable retrieval code from notebook experiments.
- Add a lightweight evaluation worksheet for retrieval quality.

## Status

Exploratory lab / secondary repo. This is not a finished benchmark suite or production system. My main proof-of-work currently lives in Stateframe, PayRail, AI Systems Notes, and my portfolio.
