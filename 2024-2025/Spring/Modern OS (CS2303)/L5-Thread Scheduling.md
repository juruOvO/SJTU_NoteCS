## Basic Concepts
CPU-IO burst cycle

## CPU Scheduler
CPU scheduling make dicisions when:
1. run->wait
2. run->ready
3. wait->ready
4. terminate
_1,4: nonpreemptive. 2,3: preemptive_

**_Gantt Chart_**

## Dispatcher
- switch context
- switch to user mode
- jump to proper location

Dispatcher latency


## Scheduling algorithms
### FCFS

### SJF
SJF always gives a minimal **average waiting time**.
Preemptive version: shortest-remaining-time-first (SRT)

Expecting the length of time:
- expotional moving average
$\tau_{n+1}=\alpha t_{n}+(1-\alpha)\tau_{n}$
$\tau \text{ is the expected time, t is the real time.}$

## Priority Scheduling

## RR
rule of thu
