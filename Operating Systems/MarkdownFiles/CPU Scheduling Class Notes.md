**Justin Ciocoi**

**Oct. 12, 2023**

# CSCI 375 Class Notes

## CPU Scheduling

****

### First-Come First-Served Scheduling

****

- Fairly self explanatory

- The *convoy effect* refers to the placement of short process after long ones, leading to a higher average waiting time

- **CPU-Bound Process**
  
  - Process that is bottlenecked by the usage or speed of the CPU - the process "waits" on the CPU

- **I/O-Bound Process**
  
  - Process that is bottlenecked by the I/O of the system - the process "waits" on the I/O

<img title="" src="file:///Users/justin/Pictures/marktextImages/9d83b8b0e940785849ddc5e75f742d57c03a75e5.png" alt="" data-align="center" width="517">

### Shortest Job First Scheduling

****

- This guarantees *minimum average waiting time*

- This algorithm is unrealistic to implement in real systems due to the complication of the system not knowing how long each process will take to start 

<img title="" src="file:///Users/justin/Pictures/marktextImages/afbdf196342858784f7eac6a9333e1731be483c9.png" alt="" data-align="center" width="511">

- As far as determining the length, in time, of the next CPU length, the best a system can do is estimate it based on previous bursts

<img title="" src="file:///Users/justin/Pictures/marktextImages/0f52a6269232812b5e14c6a3505e4a06604d0fe5.png" alt="" data-align="center" width="444">

- How is this estimation done?
  
  - Let $t_n$ be the length of the nth CPU burst
  
  - $\tau_{n+1}$ is the predicted value of the next CPU burst
  
  - $\alpha, 0\le \alpha\le1$
  
  - Define:
    
    - $\textcolor{green}{\tau_{n+1}=\alpha t_n+(1-a)\tau_n}$
    
    - commonly, $\alpha=\frac 1 2$
    
    - We can recursively define $\tau$ and expand the formula to:
    
    - $\textcolor{green}{\tau_{n+1}=\alpha t_n+(1-\alpha)\alpha t_{n-1}+...+(1-\alpha)^j\alpha t_{n-j}+...+(1-\alpha)^{n+1}\tau_0}$
  
  - Since both $\alpha$ and $(1-\alpha)$ are less than or equal to 1, each successive term is less and less weighted than its predecessor
  
  - If $\alpha$ is set to 0, *recent history* does not count
  
  - If $\alpha$ is set to 1, only the single previous CPU burst count

- *Shortest Remaining Time First Scheduling* employs preemptive scheduling to allow for the concepts of varying arrival times and preemption

<img title="" src="file:///Users/justin/Pictures/marktextImages/0f8bf09cdc92a46fae55e4377a0d7c5ee5e2e966.png" alt="" width="438" data-align="center">

### Priority Scheduling

****

- Under priority scheduling, a priority number, which is an integer, is associated with each process 

- The CPU is allocated the process with highest priority
  
  - Can be either *preemptive or non-preemptive*

- Shortest Job First scheduling is a priority scheduling algorithm where the priority is the predicted next CPU burst time

- *Problem: Starvation*
  
  - Low priority processes might never get the chance to execute

- *Solution: Aging* 
  
  - As time progresses, we can increase the priority of a process such that older processes are more heavily prioritized

<img title="" src="file:///Users/justin/Pictures/marktextImages/c984c2ff8707c273fca02ae99405b5c59641955f.png" alt="" data-align="center" width="444">
