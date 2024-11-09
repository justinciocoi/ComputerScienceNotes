**Justin Ciocoi**
**Oct. 21, 2023**

# CSCI 375 Homework 3

### Chapter 5 Exercises

##### 5.2

****

CPU Scheduling can be either preemptive or non preemptive. Preemptive CPU scheduling allows incoming processes to interrupt currently executing processes based on scheduling algorithms, whereas nonpreemptive scheduling does not allow the currently executing process to be interrupted

****

##### 5.3

****

- ***Nonpreemptive scheduling is used for all parts***

- *a)*

- - For a FCFS algorithm, the processes will be serviced in order of their arrival times.
  
  - First $P_1$ will be executed, then $P_2$, then $P_3$ 
  
  - $P_1$ arrives at $0$, starts at $0$, and exits at $8$
    
    - Turnaround time $8-0=8$
  
  - $P_2$ arrives at $0.4$, starts at $8$ and exits at $12$
    
    - Turnaround time $12-0.4=11.6$
  
  - $P_3$ arrives at time $1$, starts at $12$ and exits at $13$
    
    - Turnaround time $13-1=12$
  
  - Average Turnaround Time 
    
    - $8+12+11.6=31.6$
    - $\textcolor{blue}{\approx 10.5333}$

****

- *b)*
  
  - For a SJF algorithm, process $P_1$ will first be processed at time $0.0$ 
  - The process will run for 8 seconds and at time $8$, a scheduling decision will be made
  - at time $8$ both $P_2$ and $P_3$ have arrived, so the shorter of the two will be executed first
  - Therefore, $P_3$ will be executed, then $P_2$ 
  - $P_1$ arrives at $0$, starts at $0$ and exits at $8$
    - Turnaround time $8-0=8$
  - $P_3$ arrives at $1$, starts at $8$ and exits at $9$
    - Turnaround time $9-1=8$
  - $P_2$ arrives at $0.4$, starts at $9$, and exits at $13$
    - Turnaround time $13-0.4=12.6$
  - Average Turnaround Time
    - $8+8+12.6=28.6$
    - $\textcolor{blue}{\approx9.5333}$

****

- *c)*
  
  - In this case, the first decision will be made at time $1$
  - All processes will have arrived so they will execute in order of shortest to longest
  - $P_3$ -> $P_2$ -> $P_1$ 
  - $P_3$ arrives at $1$, starts at $1$, and exits at $2$
    - Turnaround time $2-1=1$
  - $P_2$ arrives at $0.4$, starts at $2$, and exits at $6$
    - Turnaround time $6-0.4=5.6$
  - $P_1$ arrives at $0$, starts at $6$, and exits at $14$
    - Turnaround time $14-0=14$
  - Average Turnaround Time
    - $1+5.6+14=20.6$
    - $\textcolor{blue}{\approx6.8667}$

****

##### 5.4

****

- *a)*
  
  <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/5753c4d970583b3f55d6a7d54dc4b24f2eed8e66.png" alt="" data-align="center" width="396">

****

- *b) Turnaround Times*

- *all arrive at time 0, so turnaround time is equal to exit time*
  
  - **FCFS**
    
    - $P_1$ exits at $2$
    
    - $P_2$ exits at $3$
    
    - $P_3$ exits at $11$
    
    - $P_4$ exits at $15$
    
    - $P_5$ exits at $20$
  
  - **SJF**
    
    - $P_1$ exits at $3$
    
    - $P_2$ exits at $1$
    
    - $P_3$ exits at $20$
    
    - $P_4$ exits at $7$
    
    - $P_5$ exits at $12$
  
  - **Non-Preemptive Priority**
    
    - $P_1$ exits at $15$
    
    - $P_2$ exits at $20$
    
    - $P_3$ exits at $8$
    
    - $P_4$ exits at $19$
    
    - $P_5$ exits at $13$
  
  - **Round-Robin (Time quantum 2 seconds)**
    
    - $P_1$ exits at $2$
    
    - $P_2$ exits at $3$
    
    - $P_3$ exits at $20$
    
    - $P_4$ exits at $13$
    
    - $P_5$ exits at $18$

****

- *c) Waiting Times*

- *all processes arrive at $0$ so waiting time is equal to start time*
  
  - **FCFS**
    
    - $P_1$ starts at $0$
    
    - $P_2$ starts at $2$
    
    - $P_3$ starts at $3$
    
    - $P_4$ starts at $11$
    
    - $P_5$ starts at $15$
    
    - Average $0+2+3+11+15=31$
      
      - $31/5=\textcolor{blue}{6.2}$
  
  - **SJF**
    
    - $P_1$ starts at $1$
    
    - $P_2$ starts at $0$
    
    - $P_3$ starts at $12$
    
    - $P_4$ starts at $3$
    
    - $P_5$ starts at $7$
    
    - Average $1+0+12+3+7=23$
      
      - $23/5=\textcolor{blue}{4.6}$
  
  - **Non-Preemptive Priority**
    
    - $P_1$ starts at $13$
    
    - $P_2$ starts at $19$
    
    - $P_3$ starts at $0$
    
    - $P_4$ starts at $15$
    
    - $P_5$ starts at $8$
    
    - Average $13+19+0+15+8=55$
      
      - $55/5=\textcolor{blue}{11}$
  
  - **Round Robin**
    
    - $P_1$ starts at $0$
    
    - $P_2$ starts at $2$
    
    - $P_3$ starts at $12$
    
    - $P_4$ starts at $9$
    
    - $P_5$ starts at $13$
    
    - Average $0+2+12+9+13=36$
      
      - $36/5=\textcolor{blue}{7.2}$

****

- *d) Minimum Average Waiting Time*
  
  - As shown in part *c)*, the algorithm that provides the shortest average waiting time of $4.6$ seconds is the **SJF** scheduling algorithm

****

##### 5.5

****

- *a)*
  ![](C:\Users\Justin\Pictures\marktextImages\290529aa9e782fc39cb223c95a1a76e15ad791ad.png)

****

- *b) Turnaround Times*
  
  - $P_1$ arrives at $0$ and exits at $20$
    
    - $20-0=20$
  
  - $P_2$ arrives at $25$ and exits at $80$
    
    - $80-25=55$
  
  - $P_3$ arrives at $30$ and exits at $90$
    
    - $90-30=60$
  
  - $P_4$ arrives at $60$ and exits at $75$
    
    - $75-60=15$
  
  - $P_5$ arrives at $100$ and exits at $120$
    
    - $120-100=20$
  
  - $P_6$ arrives at $105$ and exits at $115$
    
    - $115-105=10$

****

- *c) Waiting Times*
  
  - $P_1$ arrives at $0$ and starts at $0$
    
    - $0-0=0$
  
  - $P_2$ arrives at $25$, starts at $25$, pauses at $35$, resumes at $45$, pauses again at $55$, and resumes again at $75$
    
    - $(25-25)+(45-35)+(75-55)=0+10+20=30$
  
  - $P_3$ arrives at $30$, starts at $35$, pauses at $45$, resumes at $55$, pauses again at $60$, and resumes again at $80$
    
    - $(35-30)+(55-45)+(80-60)=5+10+20=35$
  
  - $P_4$ arrives at $60$ and starts at $60$
    
    - $60-60=0$
  
  - $P_5$ arrives at $100$,  starts at $100$, pauses at $105$. and resumes at $115$
    
    - $(100-100)+(115-105)=0+10=10$
  
  - $P_6$ arrives at $105$ and starts at $105$
    
    - $105-105=0$

****

- *d) CPU Utilization*
  
  - $P_{idle}$ is active for a total of $15$ seconds of the total $120$
  
  - Thus, the CPU Utilization can be found by dividing the active time by the total time
  
  - $UtilRate = 105/120=0.875=\textcolor{blue}{87.5\%}$

****

##### 5.6

****

- By differentiating between different levels with different time quantum sizes, an algorithm is given more flexibility in how it services processes of different priority. By allowing processes to slowly move into higher priority queues, this would help to reduce starvation by forcing processes to run.

****

##### 5.7

****

- *a)*
  
  - SJF is, in essence, a priority scheduling algorithm where priority is decided by a process' remaining time

- *b)*
  
  - A *multilevel* feedback queue inherently has multiple levels of CPU scheduling algorithms. One of these can be a FCFS algorithm

- *c)*
  
  - FCFS is a priority scheduling algorithm where priority is decided by a process' arrival time

- *d)*
  
  - You can think of an SJF algorithm as a round robin algorithm where the time quantum is variable and set by the shortest remaining length of a process

****

##### 5.11

****

A voluntary context switch occurs when a process has given up control of the CPU because it requires a resource that is currently unavailable, so it is more likely to occur in I/O bound operations
A non-voluntary context switch occurs when the CPU has taken away from a process, such as when the time quantum has expired or a higher priority process arrives, so it is more likely to occur in CPU bound processes 

****

##### 5.15

****

- *a)*
  
  - if $\alpha$ is set to 0 and $\tau_0$ is set to 100 milliseconds, only the last term in the formula will not be multiplied by $\alpha$ (0). Therefore, $\tau_{n+1}=0+0+....+0+(1-\alpha)^{n+1}*\tau_n=(1-0)^{n+1}*\tau_n=\tau_n=100ms$
  
  - The algorithm will use only the first CPU burst to determine the length of the upcoming one

- *b)*
  
  - if $\alpha$ is set to 0.99 and $\tau_0$ is set to 10 milliseconds, then $\tau_n$ will be determined almost entirely by $t_n$ since this term will be weighted with a weight of $\alpha$, or 0.99, and the next highest weighted term is weighted with a weight of $(1-\alpha)$ or $(1-0.99)=0.01$ 
  - Thus the algorithm will almost exclusively use the most recent CPU burst when predicting the length of the upcoming one

**** 

##### 5.18

****

- *a)*
  ![](C:\Users\Justin\Pictures\marktextImages\e88fc4c57938fe8e146ba97147e7d65f3c32445c.png)

- *b) Turnaround Times*
  
  - $P_1$ arrives at $0$ and exits at $15$
    
    - $15-0=15$
  
  - $P_2$ arrives at $0$ and exits at $85$
    
    - $85-0=85$
  
  - $P_3$ arrives at $20$ and exits at $65$
    
    - $65-20=45$
  
  - $P_4$ arrives at $25$ and exits at $70$
    
    - $70-25=45$
  
  - $P_5$ arrives at $45$ and exits at $50$
    
    - $50-45=5$
  
  - $P_6$ arrives at $55$ and exits at $60$
    
    - $60-55=5$

- *c) Waiting Times*
  
  - $P_1$ arrives at $0$ and starts at $0$
    
    - $0-0=0$
  
  - $P_2$ arrives at $0$, starts at $15$, pauses at $20$, and resumes at $70$
    
    - $(15-0)+(70-20)=15+50=65$
  
  - $P_3$ arrives at $20$, starts at $20$, pauses at $30$, resumes at $40$, pauses again at $45$, and resumes again at $60$
    
    - $(20-20)+(40-30)+(60-45)=0+10+15=25$
  
  - $P_4$ arrives at $25$, starts at $30$, pauses at $40$, resumes at $50$, pauses again at $55$ and resumes again at $65$ 
    
    - $(30-25)+(50-40)+(65-55)=5+10+10=25$
  
  - $P_5$ arrives at $45$ and starts at $45$
    
    - $45-45=0$
  
  - $P_6$ arrives at $55$ and starts at $55$
    
    - $55-55=0$

****

##### 5.22

****

- *a)*
  
  - For a time quantum of 1 millisecond, the 10 I/O processes will use that 1 millisecond as well as a 0.1 context switching overhead
    
    - The CPU utilization is therefore $1/1.1\approx 91\%$

- *b)*
  
  - For a time quantum of 10 milliseconds, each I/O process uses 1.1 milliseconds (1 msec execution, 0.1 msec overhead) and the CPU executes for 10 milliseconds as well as a 0.1 msec context switch
  
  - So, a total of 21.1 msecs pass and 20 of those are used for computation
    
    - CPU Utilization is therefore $20/21.1\approx94\%$

****

##### 5.35

****

- *a)*
  
  - These processes cannot be scheduled using rate monotonic scheduling, which is illustrated in the below Gantt Chart
  
  - <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/0edd3c197c6eaf500831c53c26353b124ce173f2.png" alt="" data-align="center" width="382">

- *b)*
  
  - <img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/15bca8d0dde11461752cb411f47115ce803cc39e.png" alt="" data-align="center" width="538">

****

### Chapter 6 Exercises

##### 6.2

****

    *Busy waiting* refers to the technique in which a process checks a condition repeatedly to see if it can continue. This can be implemented in the form of a while loop that does nothing but check a condition, thereby blocking progress until that condition is met. Busy waiting can be avoided altogether by using the semaphore implementations from section 6.6.2 which uses a semaphore struct containing a list that will be used for queuing process rather than engaging in busy waiting. 

****

##### 6.3

---

    During a thread's spinlock loop, it consumes CPU cycles while waiting, thus rendering a single processor system unable to execute another instruction. However, in a multi-processor systems the existence of other threads able to execute greatly helps to prevent starvation.

---

##### 6.4

****

First let us define the wait and signal operations

- The definition of `wait()` is as follows
  
  - ```cpp
    wait(S)
    {
        while(S <= 0)
            ; // busy wait
    
        S--;
    }
    ```

- The definition of `signal()` is as follows
  
  - ```cpp
    signal(S)
    {
        S++;
    }
    ```

If process $P_0$ and $P_1$ are running concurrently with semaphore $S$, and both processes enter the wait operation almost simultaneously, both might see the semaphore as 1 and decrement, thus both assuming they have the lock and entering the critical section. This clearly violates the principle of mutual exclusion

---

##### 6.5

---

    To illustrate this concept we will consider a semaphore `mutex` that will be initialized to $1$, and three processes, $P_1, P_2,$ and $P_3$. Each process can be roughly described as follows:

```cpp
process
{
    wait(mutex);

    //critical section

    signal(mutex);
}
```

We will use `wait()` and `signal()` functions roughly as described in the previous problem. Now let us look at the steps of how a binary semaphore can implement mutual exclusion across these three processes

1. `mutex` is initialized to $1$

2. $P_1$ executes `wait(mutex)`, sees `mutex` initialized to $1$, and decrements `mutex` to $0$ before proceeding on to its critical section

3. $P_2$ and $P_3$ both arrive simultaneously almost immediately after $P_1$ and both execute `wait(mutex)` but since $P_1$ had set `mutex` to 0, they are both blocked from entering their critical sections

4. Eventually, $P_1$ will exit its critical section and call `signal(mutex)`, incrementing `mutex` to $1$. 

5. Depending on the scheduler, either $P_2$ or $P_3$ will unblock and decrement `mutex` once again to $0$ 

6. The process repeats and eventually whichever is left will be allowed to execute its critical section

While this example shows only 3 concurrent processes, while $P_1$ is running, any amount of processes can arrive and they will all be blocked and appropriately queued by the scheduler for once $P_1$ has finished its critical section.

---

##### 6.6

---

    To illustrate how a data race condition is possible in such a scenario, we will consider the account balance beginning at $$1000$. Let us say the husband calls `withdraw(500)` and concurrently the wife calls `deposit(200)`. If these operations are not executed atomically, then it is possible for both function calls to execute on the initial amount. Thus, when the processes exit, the last one to exit will update and overwrite the returned value of the other function call. For example, husband updates the balance to $$500$, and immediately after the wife overwrites it to $$1200$. In order to avoid this, we can implement a semaphore to provide mutual exclusion such that these functions will execute the critical section of balance updating atomically. 

---
