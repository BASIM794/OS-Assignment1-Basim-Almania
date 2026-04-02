# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A thread is a smaller unit of execution, whereas a process is an independent program in execution with its own memory space. Threads are lighter and can be created more quickly than processes, which have higher overhead due to the need to allocate separate memory and system resources.

Since the simulation does not need memory segregation between tasks, threads were employed in place of processes in this assignment. Effective context switching and shared access to data structures such as the ready queue are made possible by threads. This accelerates the simulation and brings it closer to how multithreading is implemented in actual operating systems.**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:A process in Round-Robin scheduling is preempted and put at the end of the ready queue if it does not complete within the allotted time quantum. This keeps the CPU from being monopolized by any one process and guarantees equity for all processes.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
▶ P1 executing quantum [3000ms]
Remaining time: 96ms
P1 yields CPU for context switch

➕ P1 added to ready queue
│ [P3 → P4 → ... → P18 → P1]
```
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:In this instance, process P1 ran for the entire 3000 ms time quantum, but there were still 96 ms left. Consequently, it was re-added to the end of the ready queue after yielding the CPU. This behavior illustrates how Round-Robin scheduling ensures that each process receives an equal amount of CPU time by cycling across processes.**
[Explain what's happening in the output snippet you pasted]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.
1.New:
P1 is in the New state when it is first created using new Thread(process) before being added to the ready queue.
2.Runnable:
After being added to the ready queue and before execution, P1 is in the Runnable state. For example, when it appears in the queue:[P2 → P3 → ... → P18 → P1]
3.Running:
P1 enters the Running state when it starts executing: ▶ P1 executing quantum [3000ms]
4.Waiting:
During execution, P1 enters the Waiting state when Thread.sleep() is called to simulate execution time. This is reflected in the progress bar updates:
⚡ Quantum progress: [███████████████] 100%
5.Terminated:
P1 reaches the Terminated state when it finishes execution completely:
▶ P1 executing quantum [96ms]
Remaining time: 0ms
✓ P1 finished execution!
This sequence clearly shows how a thread transitions through all lifecycle states during the simulation.   

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Handling Requests from Web Servers


**Description**: Multiple user requests are handled concurrently by a web server; each request can be viewed as a thread.



**Why Round-Robin works well here**: By allocating a time slice to each request, Round-Robin guarantees fairness by preventing any one request from blocking others. This enhances responsiveness and guarantees effective service for all users.



### Example 2:Task Scheduling in the Operating System



**Description**: Many apps (such as browsers, audio players, and background processes) are scheduled simultaneously by modern operating systems.


**Why Round-Robin works well here**: It guarantees that every process receives CPU time on a regular basis, resulting in a seamless user experience. In addition to preventing famine, this enhances system responsiveness


---

## Summary

**Key concepts I understood through these questions:**
1.The distinction between threads and processes 
2.The behavior of round-robin scheduling
3.The lives and states of threads


**Concepts I need to study more:**
1.Sophisticated algorithms for scheduling
2.Synchronization and deadlocks 
