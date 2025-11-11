# Linux CFS (Completely Fair Scheduler) Simulation
It shows how CPU-bound and IO-bound processes are scheduled based on virtual runtime (vruntime) and weights derived from priority. Higher-priority processes get proportionally more CPU time, while all processes still receive a fair share according to their weights.

## Working
## 1. Process Loading
Processes are defined in a JSON file (e.g., processes.json).

## 2.Scheduling
-All processes are pushed into a priority queue ordered by vruntime.
-The scheduler (cfs::schedule) repeatedly picks the process with the smallest vruntime and simulates a time slice.
-CPU-bound tasks consume CPU time directly; IO-bound tasks simulate I/O wait with this_thread::sleep.

## Logging
-Each process execution is recorded in a log (start and end timestamps in nanoseconds).
-Results are saved as a CSV file.

## 4.Visualization
The Python script plotgraph.py reads the CSV and produces a Grantt chart graph showing process execution over time.
