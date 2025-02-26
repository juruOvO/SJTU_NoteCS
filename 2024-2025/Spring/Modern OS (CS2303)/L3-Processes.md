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

### Process Control Block (PCB)
Information associated with each process (a.k.a. Task Control Block)
- Process state
- Program counter
- CPU registers
- CPU scheduling info
- Memory-management info
- Accounting info
- IO status info
[PCB Sturcture](L3_p4.png)

## Process Scheduling
---
**Process scheduler** selects an available processes for next execution on CPU core.

**Goal:** Maximize CPU use. Quickly switch processes onto CPU core.

Maintaining:
- Ready Queue
- Wait Queue

### CPU Switch From Process to Process
Context Switch:
![[Pasted image 20250226085856.png]]
	- Context switch time is pure overhead.

Schedulers:
- Two levels of schedulers:
	- **Long-tern Scheduler**
	- **Short-tern Scheduler**
![[Pasted image 20250226090248.png]]

- 2 types of process
	- I/O-bound process
	- CPU-bound process

## Process Operations
---
### Process Creation
- _**Parent Process Create Children Process**_
- Process identified and managed via a **Process Identifier (pid)**

### Parent and CHild Process Relations
- Resources sharing options:
	- p and c share all resources
	- c share subset of p's resources
	- share no resources
- Execution options
	- concurrently
	- p wait until c terminate
- Address space options
	- c duplicate addr space of p
	- c has a program loaded into it

![[Pasted image 20250226091112.png]]

### Process Termination
![[Pasted image 20250226091727.png]]![[Pasted image 20250226092023.png]]

## Interprocess Communication
---
### Example: Chrome Browser
- 3 different types of processes:
	- Browser
	- Renderer
	- Plug-in

### Interprocess Communication (IPC)
	Two models of IPC
		