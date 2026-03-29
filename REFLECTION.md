# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

[Write your answer here. Discuss specific concepts like thread creation, thread states, how threads execute concurrently, what surprised you, etc.]
A process is a self-contained execution environment that includes its own private memory space (heap, stack, and data), while a thread is a smaller unit of execution that lives within a process and shares that process's resources. The primary difference lies in resource allocation: processes are heavy and isolated, whereas threads are lightweight and share the same address space. In this assignment, we used threads because creating processes involves significant overhead in terms of memory and CPU time for context switching. Using threads allows the simulation to run efficiently because they can communicate and share the "CPU" state without the complex inter-process communication
---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**

[Describe the specific challenge. Was it understanding the code? Implementing a feature? Using Git? Explain what made it difficult and how it relates to the course concepts.]
In Round-Robin scheduling, if a process does not complete its execution within its allocated time quantum, it is preempted by the scheduler to ensure fairness. The scheduler moves the process from the Running state back to the end of the Ready Queue, allowing the next process in line to have its turn. This prevents any single "CPU-bound" process from hogging resources, ensuring that every process makes steady progress. Essentially, the process is paused, its current state is saved (context switching), and it waits for its next turn in the circular rotation.
---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

[Describe your problem-solving approach. Did you read documentation? Ask for help? Debug systematically? What resources did you use? What strategies worked?]
The lifecycle of a thread in this simulation moves through distinct stages as it interacts with the scheduler and the virtual CPU.

New: P1 is in the New state when the process object is first instantiated in the code but has not yet been admitted to the Ready Queue.

Runnable: P1 enters the Runnable state once it is added to the Ready Queue, meaning it is prepared and waiting for the scheduler to pick it for execution.

Running: P1 is in the Running state when the scheduler assigns it to the "CPU," and it begins executing its instructions (decrementing its remaining time).

Waiting: P1 would enter the Waiting state if it had to pause for an I/O operation or a synchronization signal (though in basic RR simulations, it usually stays in the Ready Queue if it's just waiting for a turn).

Terminated: P1 enters the Terminated state once its remaining execution time reaches zero and it is removed from the system.
---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**

[Give specific examples from real applications you use (web browsers, games, mobile apps, etc.). Explain why threads are useful in those scenarios. Connect to what you learned in this assignment.]

---Example 1: Web Servers
Description: A web server (like Apache or Nginx) handling multiple incoming requests from different users simultaneously.
Why Round-Robin works well here: It provides fairness and responsiveness. By using threads for each request and scheduling them with Round-Robin, the server ensures that no single user’s large file download completely blocks other users from loading small text pages, providing a smooth experience for everyone.

Example 2: Time-Sharing Operating Systems
Description: A multi-user environment where several people are logged into a single server to perform interactive tasks like coding or document editing.
Why Round-Robin works well here: It is ideal for interactive tasks because it provides a guaranteed maximum response time. Users don't experience "lag" because the scheduler rotates through every user's active threads quickly enough that it feels like everyone has their own dedicated processor.

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
