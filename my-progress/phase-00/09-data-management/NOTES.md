# Phase 0 · 09 Data Management
Date: 2026-09-19

## What this lesson does
Loading/streaming/caching datasets with Hugging Face `datasets`, format
conversion, reproducible splits, versioning large files (.gitignore/LFS/DVC).

## What broke
Nothing broke, but noted: lesson text says `pip install datasets huggingface_hub`
plainly. Running it as `uv pip install ...` instead — same result, but respects
the active venv and matches the workflow from lesson 06. Plain `pip install`
is only correct verbatim inside a Dockerfile RUN line, where there's no venv
to protect and uv isn't installed by default.

## What I did not fully get
N/A.

## Exercises
- [ ] pending — load a dataset, convert formats, split train/val/test
