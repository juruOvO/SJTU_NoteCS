## Outline
- Processes
- Threads
- CPU scheduling
- Process synchronization
- Deadlocks

## Processes
---
### Concept
_Process is a program in execution._
[Difference between Process and Program](L3_p1.png)
- One program can become mutiple processes.
### Process in Memory
Process memory can be divided into 4 parts:
- Stack
- Heap
- Data Section
- Text Section
Process activity will be recorded in:
- Program counter (PC)
- Process registers contents
[Process Memory Structure](L3_p2.png)

_Heap_ in OS is not related to _Heap_ in DS, while *stack* in OS is related to _stack_ in DS.

- **The size of text and data is fixed.**
- The Stack and Heap can vary dynamically
	- Stack:
		- Grow: **Call func**
		- Shrink: **Func ret**
	- Heap:
		- Grow:  **Allocate memory**
		- Shrink: **Return memory**

### Process State
- New
- Ready
- Running
- Waiting
- Terminated
[Process State Diagram](L3_p3.png)
