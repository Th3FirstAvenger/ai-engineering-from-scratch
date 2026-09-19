# Phase 0 · 06 Python Environments
Date: 2026-09-19

## What this lesson does
Isolating dependencies per project with uv/venv/conda, pyproject.toml, lockfiles.

## What broke
Root .venv had torch==2.2.2 (Intel Mac ceiling, no arm64/newer wheels)
paired with numpy 2.5.3 — torch 2.2.2 was compiled against NumPy 1.x.
Import worked but warned "Failed to initialize NumPy: _ARRAY_API not
found". Same failure mode as the lesson's CUDA mismatch example (#5),
just NumPy instead of CUDA. Fixed with `uv pip install "numpy<2"`.

Also ran `uv init my-ai-project` at one point, which was not part of the
lesson — it resolved torch==2.14.0 (no macOS x86_64 wheel). Deleted it.

## What I did not fully get
N/A — this was a real dependency-hell hit, not a comprehension gap.

## Exercises
- [x] 1 env_setup.sh — ran, checks passed after the numpy pin
- [x] 2 second venv, isolated numpy version confirmed
- [x] 3 pyproject.toml pinned to `torch==2.2.2` + `numpy<2` (Intel Mac ceiling)
- [x] 4 global install without venv — observed site-packages location, uninstalled
