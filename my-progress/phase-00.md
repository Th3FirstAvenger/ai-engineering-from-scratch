# Phase 0 — Setup and Tooling

## 01 Dev Environment — done (2026-09-19)
Ran `verify.py --route beginner`, hello world in Rust. Julia was already installed
via juliaup (1.13.0) — just couldn't tell because `.juliaup/bin` was duplicated
three times in `~/.zshrc` PATH (manual export + juliaup's own managed block).
Cleaned the manual duplicate. Pending: Python/TS hello world.

## 02 Git and Collaboration — done (2026-09-19)
Forked the repo, `origin` = my fork, `upstream` = author's repo, working on `my-progress` branch.

## 03 GPU Setup and Cloud — done, already knew
Mac is Intel (i7-9750H), no CUDA/MPS. Plan: RunPod for phases 10-12.

## 04 APIs and Keys — done, already knew

## 05 Jupyter Notebooks — done, already knew

## 06 Python Environments — done (2026-09-19)
Root `.venv` had torch==2.2.2 (Intel Mac ceiling) paired with numpy 2.5.3 —
torch 2.2.2 was built against NumPy 1.x, threw an ABI warning on import.
Fixed with `uv pip install "numpy<2"`. Also: `uv init` resolves torch
2.14.0 by default, which has no macOS x86_64 wheel — pin `torch==2.2.2`
explicitly in any pyproject.toml on this machine.

## 07 Docker for AI — done (2026-09-19)
No NVIDIA GPU here. Had to drop `--gpus all` from `docker run` and comment
out the `deploy:` (nvidia driver) block in docker-compose.yml, or
`docker compose up` fails trying to select a driver that doesn't exist.
Exercises 3-4 (flask container, image size comparison) still pending.

## 08 Editor Setup — done, already knew

## 09 Data Management — done (2026-09-19)
Lesson says `pip install ...` — using `uv pip install ...` instead to stay
inside the active venv (see 06). Loading/splitting a real dataset: pending.

## 10 Terminal and Shell — done, already knew

## 11 Linux for AI — done, already knew

## 12 Debugging and Profiling — done, already knew

---
**Phase 0 complete.** Next: `phases/01-math-foundations/01-linear-algebra-intuition`.
