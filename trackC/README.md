
---

## 📁 **trackC/README.md**

```markdown
# Track C: Overlapping Communication and Computation with Non‑blocking Collectives

## Objective
Learn how non‑blocking collective operations can hide communication latency by overlapping it with useful computation. You will compare a blocking `MPI_Allreduce` with a non‑blocking version (`MPI_Iallreduce`) and measure the overlap efficiency.

## Provided Code
- `blocking_allreduce.c` – Uses `MPI_Allreduce` (blocks until complete)
- `nonblocking_allreduce.c` – Uses `MPI_Iallreduce` + `MPI_Wait`, with a dummy computation inserted between initiation and wait.

Both codes simulate a distributed workload: each process computes a local sum (or performs a dummy loop) and then calls the collective to average the results.

## Steps

### 1. Compile the codes
```bash
mpicc -o blocking_allreduce blocking_allreduce.c
mpicc -o nonblocking_allreduce nonblocking_allreduce.c
