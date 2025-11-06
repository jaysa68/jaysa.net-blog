---
date:
    created: 2025-03-18
categories:
    - Tech
---

# CS162 Operating Systems Cheatsheet

<!-- more -->

## Scheduling

`Response time for P`
: time to when proc gets first scheduled

`completion time`
: waiting time + run time

`average completion time`
: avg of all procs completion times
: = sum(burst time all procs) / (num procs)

`latency`
: user-perceived time to do some task

`throughput`
: the rate at which tasks are completed

`scheduling overhead`
: the time to switch from one task to another

`predictability`
: variance in response times for repeated requests

`fairness`
: equality in performance perceived by one task

`starvation`
: the lack of progress for one task, due to resources being allocated to different tasks

`convoy effect`
: lots of small tasks build up behind long tasks

---

- Goal of a scheduler is to **minimize latency** while **maximizing throughput**.

- Any scheduling property that favors a **fixed property** for scheduling leads to starvation.
    - ex. Shortest Job First (SJF)

###Schedulers

Preemptible

- STCF (Shortest Time to Completion First) - schedule the task with the least amount of time left


Non-preemptible

- Any non-preemptible scheduling policy suffers from the convoy effect

- FCFS/FIFO


insert thread life cycle chart

## Virtual Memory

###Base & Bound###

Cons: 

1. No expandable memory
1. No memory sharing
1. Non-relative Memory Addresses
1. External Fragmentation
1. Internal Fragmentation 
