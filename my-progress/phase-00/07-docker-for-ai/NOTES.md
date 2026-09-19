# Phase 0 · 07 Docker for AI
Date: 2026-09-19

## What this lesson does
Dockerfile + docker-compose for reproducible AI dev environments, GPU passthrough
via NVIDIA Container Toolkit.

## What broke
No NVIDIA GPU on this Mac (Intel, no eGPU support in Docker Desktop either).
Had to strip `--gpus all` from both `docker run` commands and comment out
the `deploy:` block (nvidia driver reservation) in docker-compose.yml —
otherwise `docker compose up` fails trying to select a driver that doesn't
exist. Lesson's own "No GPU?" section covers this, just easy to miss until
compose actually errors.

## What I did not fully get
N/A.

## Exercises
- [x] 1 built image, `torch.cuda.is_available()` → False (expected)
- [x] 2 compose stack up (deploy block removed), Qdrant reachable
- [ ] 3 flask on port 5000
- [ ] 4 devel vs runtime image size comparison
