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
- Two models of IPC
	- Shared memory
	- Meesage passing
![[Pasted image 20250226092822.png]]
![[Pasted image 20250226093009.png]]

## IPC: Shared Memory
---
![[Pasted image 20250226093455.png]]
### Producer-Consumer Problem
- 2 variaaitons:
	- Unbounded-buffer
	- Bounded-buffer

### Bounded-buffer 
- shared data
```C
#define BUFFER_SIZE 10 
typedef struct { . . . } item; 
item buffer[BUFFER_SIZE]; 
int in = 0; 
int out = 0;
```
Producer Process
```C
item next_produced; 
while (true) {
/* Produce an item */ 
while (((in + 1) % BUFFER_SIZE) == out) ;
 /* do nothing -- no free buffers */ 
 buffer[in] = next_produced; 
 in = (in + 1) % BUFFER_SIZE; }
```
Consumer Process
```C
item next_consumed; 
while (true) { while (in == out) ; 
/* do nothing */ 
next_consumed = buffer[out]; 
out = (out + 1) % BUFFER_SIZE; } /* consume the item in next consumed */
```

Optimization:
Fully use buffer slots.
1. Add a recorder
2. Avoiding (in == out) when full

## IPC: Message Passing
---
- Two operations:
	- **Send**
	- **Receive**
- If P and Q want to communicate, theey have to:
	- Establish a _communication link_
	- Send/Receive
- Two types of communication:
	- Direct
	- Indirect

### DIrect communication
- Process must **Name** each other explicitly
- The link is commonly bidirectional (may be unidirectional)
- **Exactly ONE link** between every communication pair

### Indirect communication
- Messages are directed and received from **Mailboxes (ports)**
	- Each mailbox has a unique id
	- process can communicate only if they share a mailbox
- uni or bi-directional (commonly bi)
- **Several links** can exist between every communication pair
![[Pasted image 20250226101742.png]]
### Message Passing: Synchronization
- **blocking** or **non-blocking**
![[Pasted image 20250226101923.png]]

### Unix Example
![[Pasted image 20250226102036.png]]

### Ordinary Pipes
- Unidirectional
- 2 ends
	- write end
	- read end
![[Pasted image 20250226102336.png]]

### Named Pipes
- bidirectional

### Using pipe
1. Create a pipe and check for errs
```C
int mypipe[2]; 
if (pipe(mypipe)) { 
fprintf (stderr, "Pipe failed.\n"); 
return -1; }
```

2. Fork your threads

3.  Close the pipes you don't need in that thread
```C
close(mypipe[1]);//write-end
close(mypipe[0]);//read-end
```

![[Pasted image 20250226102906.png]]
## Communication in Client-Server System
---
- Sockets
- 


