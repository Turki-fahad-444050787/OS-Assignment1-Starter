# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A **Process** is an independent execution unit that has its own dedicated memory space and resources managed by the Operating System. In contrast, a **Thread** is often called a "lightweight process" because it exists within a process and shares the same memory heap and resources with other threads. We used threads in this assignment because they are much more efficient for a simulation; they have lower creation overhead and allow for faster communication between tasks. This allows the program to manage 18 different tasks (P1 to P18) simultaneously without exhausting the system's memory or CPU power.

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not complete its execution within the assigned **Time Quantum (4000ms)**, it is preempted by the scheduler. This means the CPU stops the current process, saves its state, and moves it to the very back of the **Ready Queue** to give other processes a fair chance. The process must then wait for its next turn to continue from where it left off.

Example from my output:
```text
  ظû╢ P1 executing quantum [4000ms]
  ظأة Quantum progress: [ظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûê] 100%
  ظ╕ P1 completed quantum 4000ms ظ¤é Overall progress: [ظûêظûêظûêظûêظûêظûêظûêظûêظûêظûêظûّظûّظûّظûّظûّظûّظûّظûّظûّظûّ] 50%
     Remaining time: 3978ms
  ظ╗ P1 yields CPU for context switch


 ## Question 3: Thread States
Question: A thread can be in different states: New, Runnable, Running, Waiting, Terminated. Walk through these states for one process (P1) from your simulation.

Your Answer:
In my simulation, the process P1 travels through several states to complete its lifecycle. It starts in the New state when the thread object is first created in the Java code before calling the start method. Once P1.start() is executed, it moves to the Runnable state, where it sits in the Ready Queue waiting for the scheduler's signal. When the CPU picks P1, it enters the Running state to execute its burst time, and it may enter the Waiting state during context switches or Thread.sleep() intervals. Finally, once P1 finishes its total execution time and the remaining time becomes zero, it moves to the Terminated state.
---
New: When the new Thread(P1) is instantiated in the main method.

Runnable: When the process is added to the Ready Queue after the start() command.

Running: When the scheduler allocates the CPU time slice to P1 and it begins processing.

Waiting: When P1 yields the CPU for a context switch or during simulated sleep intervals.

Terminated: When P1 completes its full burst time and the thread execution stops.

Question 4: Real-World Applications
Question: Give TWO real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

Your Answer:

Example 1: Web Server Request Management
Description:
A high-traffic web server, like a university registration portal, must handle hundreds of concurrent student requests for data.
Why Round-Robin works well here:
It provides fairness and high responsiveness for all users. By giving each request a small time slice using threads, the server ensures that no single user downloading a large file can block other users who are just trying to load a small text page, keeping the system balanced.

Example 2: Multiplayer Gaming Servers (e.g., Call of Duty)
Description:
In a fast-paced game like Call of Duty, the server uses threads to update the game state, player positions, and physics for everyone in the match.
Why Round-Robin works well here:
It maintains a low-latency environment which is critical for smooth gameplay. The Round-Robin algorithm cycles through every player's data updates very rapidly, ensuring that every player's actions are processed in near real-time without anyone experiencing a "freeze" while the server waits for others.

Summary
Key concepts I understood through these questions:

The difference between the memory-isolated Process and the resource-sharing Thread.

How the Ready Queue and Preemption maintain fairness in a Round-Robin system.

The complete lifecycle of a thread in Java from its creation to termination.

Concepts I need to study more:

Advanced thread synchronization methods to prevent data corruption.

How different Time Quantum values affect the overall system overhead and performance.
