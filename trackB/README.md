# Track B: Comparing MPI Collective Operations – Broadcast, Reduce, Allreduce

## Objective
Measure and compare the time taken by three different collective operations:
- `MPI_Bcast` (one-to-all broadcast)
- `MPI_Reduce` (all-to-one reduction)
- `MPI_Allreduce` (all-to-all reduction)

You will observe how their performance scales with message size and number of processes, and relate this to real‑world use in AI training.

## Provided Code
- `bcast_time.c`  – Times `MPI_Bcast`
- `reduce_time.c` – Times `MPI_Reduce`
- `allreduce_time.c` – Times `MPI_Allreduce`

All codes follow the same pattern:
- The root process prepares a data buffer.
- The collective operation is called.
- The elapsed time is measured using `MPI_Wtime()` and printed.

## Steps

### 1. Compile the codes
Open a terminal in this folder and run:
```bash
mpicc -o bcast_time bcast_time.c
mpicc -o reduce_time reduce_time.c
mpicc -o allreduce_time allreduce_time.c
