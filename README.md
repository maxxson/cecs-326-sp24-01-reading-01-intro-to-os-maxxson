# CECS 326 Reading Assignment: Introduction to Operating Systems
Maximillian Son
ID: 028865874
### Assignment Description
Answer the following questions from the Chapter 1 reading from your text- book. Be through and complete with your answers. You may work on these questions with one or two other partners, but *all* students must submit the document individually in their own repositories along with each student's name documented with the submission.

1. What are the two main functions of an operating system? 
An operating system must furnish users with an extended machine while simultaneously overseeing I/O devices and various system resources. In essence, these represent different functions.

2. What is the difference between timesharing and multiprogramming systems?
Within a timesharing system, several users can concurrently access and execute computations on a computing system through their individual terminals. 
Multiprogramming systems enable a user to execute multiple programs concurrently. While all timesharing systems are multiprogramming systems, not all multiprogramming systems are timesharing systems, as a 
multiprogramming system may operate on a personal computer with only one user.

3. The family-of-computers idea was introduced in the 1960s with the IBM System/360 mainframes. Is this idea now dead as a doornail or does it live on?
It is not dead. For instance, Intel produces Core i3, i5, and i7 CPUs with various characteristics such as speed and power consumption. Despite these differences, all machines maintain architectural compatibility. 
Their distinctions lie solely in pricing and performance, encapsulating the essence of the family concept.

4. What is the difference between kernel and user mode? Explain how having two distinct modes aids in designing an operating system.
The majority of contemporary CPUs offer two execution modes: kernel mode and user mode. In kernel mode, the CPU can execute any instruction within its instruction set and utilize all hardware features. 
Conversely, in user mode, it is limited to a subset of instructions and hardware features. The existence of these two modes enables designers to execute user programs in user mode, thereby restricting their access to critical instructions.

5. On early computers, every byte of data read or written was handled by the CPU (i.e., there was no DMA). What implications does this have for multiprogramming?
When a thread is halted, it retains values within the registers, which necessitate preservation similar to when a process is halted. Just as in multiprogramming processes, multiprogramming threads 
require individual register save areas to ensure proper management.

6. There are several design goals in building an operating system, for example, resource utilization, timeliness, robustness, and so on. Give an example of two design goals that may contradict one another.
Each system architecture possesses its own distinct set of executable instructions. Consequently, a Pentium processor cannot execute SPARC programs, and vice versa. Additionally, architectures vary in their 
bus architecture, such as VME, ISA, PCI, MCA, and SBus, as well as in the CPU's word size, typically either 32 or 64 bits. Due to these hardware disparities, developing a fully portable operating system is impractical. 
Instead, a highly portable operating system typically comprises two primary layers: a machine-dependent layer and a machine-independent layer. The machine-dependent layer accommodates the specifics of the hardware and 
necessitates separate implementations for each architecture. This layer furnishes a standardized interface upon which the machine-independent layer is constructed. Conversely, the machine-independent layer only requires 
implementation once. To ensure high portability, minimizing the size of the machine-dependent layer is imperative.

7. Which of the following instructions should be allowed only in kernel mode?
    (a) Disable all interrupts.
    (b) Read the time-of-day clock.
    (c) Set the time-of-day clock. (d) Change the memory map.
a) This operation is a critical system function that affects the entire system's ability to respond to external events. Disabling interrupts prevents the CPU from responding to external signals, which could lead to system instability or security vulnerabilities if done improperly. Therefore, this operation should only be allowed in kernel mode.
c) Setting the time-of-day clock involves modifying a system resource that affects the entire system's timekeeping. Unauthorized changes to the system time can lead to various issues, including incorrect file timestamps, authentication failures, or even security breaches (e.g., bypassing time-based security measures). Hence, this operation should only be allowed in kernel mode.
d) Changing the memory map involves altering the way memory is organized and accessed by the system. This is a critical operation that directly impacts system stability, security, and the behavior of running processes. Unauthorized changes to the memory map can lead to system crashes, data corruption, or security vulnerabilities. Therefore, this operation should only be allowed in kernel mode.

8. Consider a system that has two CPUs, each CPU having two threads (hyperthreading). Suppose three programs, P0, P1, and P2, are started with run times of 5, 10 and 20 msec, respectively. How long will it take to complete the execution of these programs? Assume that all three programs are 100% CPU bound, do not block during execution, and do not change CPUs once assigned.
The execution time of these programs can vary depending on the scheduling decisions made by the operating system. If P0 and P1 run on one CPU while P2 runs on another, the execution time will be 20 milliseconds. If P0 and P2 run on one CPU and P1 on another, it will take 25 milliseconds. When P1 and P2 are on one CPU and P0 on another, the execution time will be 30 milliseconds.
If all three programs run on the same CPU, the execution time will be 35 milliseconds.

9. What is a trap instruction? Explain its use in operating systems.
A trap instruction facilitates the transition of CPU execution mode from user mode to kernel mode. This instruction grants a user program the capability to access functions within the operating system kernel.

10. Modern operating systems decouple a process address space from the machine’s physical memory. List two advantages of this design.
Decoupling process address space from physical memory offers two main benefits: robust memory protection, keeping processes isolated for security, and efficient memory management through techniques like virtual memory, optimizing system performance and resource usage.

### Deliverables
Commit the answers to the questions in a readable file to your git repository by the due date and time indicated with your repository. Approved file submission formats are: .txt, .md, .pdf. .html (renderable) or anything that is web-readable on Github. Other formats will only be accepted with explicit approval.
