**Justin Ciocoi**

**Nov. 30, 2023**

# CSCI 375

## Homework 4

#### Chapter 7 Practice Exercises

- **7.1:** The main reason why modern operating systems implement multiple locking mechanisms is because different scenarios might require different mechanisms in order to ensure expected and optimal performance. Spin-locks will be implemented when the expected wait time is relatively small, so they are an efficient method when dealing with things like interrupt handling. Mutex locks are used when longer operations need access to shared data, and they allow waiting threads to sleep which can help to minimize CPU usage. Condition variables will be used with mutex locks in order to effectively synchronize access to shared memory. Finally, semaphores are used when there exist a certain number of identical resources that can be shared among a number of different processes.

- **7.2:** One benefit provided by Windows' slim reader-writer locks is a reduced risk of starvation for either readers or writers since neither class of process will be favored over the other. Additionally, by not using a FIFO queuing structure, Windows reduces system overhead used by synchronization processes through bypassing the need to organize and maintain a queue of waiting processes. 

- **7.3:** Within these processes, a mutex lock could be implemented using the `compareAndSwap()` hardware instruction as was used in project 3 using a boolean lock

- **7.4:** A deadlock is possible if each dining philosopher holds one chopstick and is unable to release it until acquiring a second. Since they all hold one, none of them will ever be able to acquire a second one and thus none of them will ever release the chopstick 

#### Chapter 8 Practice Exercises

- **8.2:** We can imagine a system with 3 threads, $T_1, T_2,\ \text{and}\ T_3$ and 2 resources, $R_1$ and $R_2$, where each thread needs both resources to complete. If the system begins with $T_1$ holding $R_1$ and requesting $R_2$ and $T_2$ holding $R_2$ and requesting $R_1$, then it is in an unsafe state since there is a potential for deadlock in case both processes wait for the other to release the appropriate resource. However, imagine $T_1$ finished its work with $R_1$ and releases it before $T_2$'s request times out. Then $T_2$ acquires $R_1$, completes and lets $T_1$ have both resources. Next, $T_1$ completes and makes available the resources for $T_3$ 

- **8.3:** 
  
  - **a)** The content of the need matrix can be found by subtracting the allocation matrix from the max matrix, which here will result in the following matrix:
  
  |       | A   | B   | C   | D   |
  |:----- | --- | --- | --- | --- |
  | $T_0$ | 0   | 0   | 0   | 0   |
  | $T_1$ | 0   | 7   | 5   | 0   |
  | $T_2$ | 1   | 0   | 0   | 2   |
  | $T_3$ | 0   | 0   | 2   | 0   |
  | $T_4$ | 0   | 6   | 4   | 2   |
  
  - **b)** 
    
    - First $T_0$ is serviced, and one of resource $C$ and 2 of resource $D$ will be added to the available matrix
      
      - *Available: $(1,5,3,2)$*
    
    - Next, $T_2$ can be serviced and 1 of resource $A$, 3 of resource $B$, 5 of resource $C$ and 4 of resource $D$ will be added to the available matrix
      
      - *Available: $(2,8,8,6)$*
    
    - Next, $T_1$ can be serviced, and 1 of resource $A$ will be added to the available matrix
      
      - *Available: $(3,8,8,6)$*
    
    - Next, $T_3$ can be serviced, and 6 of resource $B$ 3 of resource $C$ and 2 of resource $D$ will be added to the available matrix
      
      - *Available: $(3,14,11,8)
        $*
    
    - Finally, $T_4$ will be serviced and 1 of resource $C$ and 4 of resource $D$ will be added to the available matrix
      
      - *Available: $(3,14,12,12)$*
  
  - **c)** The request for $(0,4,2,0)$ can be immediately granted since the available resources are $(1,5,2,0)$ so there are enough of each resource for $T_1$ to be granted its requested resources

- **8.4:** This functions in a manner fairly similar to the circular wait scheme since a linear order of acquiring locks is implemented. Using containment, one lock can effectively serialize access to a whole set of resources. Circular wait will still use multiple different locks.

- **8.6:** Deadlocks occur twice per month, and cause 10 jobs to be re-run each time. Each job is worth 2 dollars and is half done when terminated.
  
  - **a)** The arguments for installing the deadlock-avoidance algorithm are that since each deadlock causes monetary loss in the form of wasted in CPU time of $$10$, so deadlock avoidance algorithms would save this monetary loss
  
  - **b)** However, since the monetary loss incurred by deadlocks is relatively small, the argument against installing the algorithm would be that the idle time could generate more value if used for additional jobs rather than deadlock avoidance

- **8.7:** Yes, a system can monitor the amount of time different threads spend waiting, and based on this monitor whether or not certain threads are starving based on given parameters

- **8.8:** 
  
  - **a)** No, a deadlock cannot occur. Since the processes will give up their resources if requested by another process, the hold and wait condition necessary for deadlocks does not occur
  
  - **b)** Indefinite blocking, or starvation, is still possible. Imagine a system where one processes requires 5 types of resource to complete but many other processes require just one type. These many resources will be constantly granted the resources they request, but the one major process might never be able to simultaneously acquire all 5 resources, leading to starvation

- **8.9:** 
  
  Need Matrix:
  
  |       | A   | B   | C   | D   |
  | ----- | --- | --- | --- | --- |
  | $T_0$ | 2   | 1   | 0   | 3   |
  | $T_1$ | 1   | 0   | 0   | 1   |
  | $T_2$ | 0   | 2   | 0   | 0   |
  | $T_3$ | 4   | 1   | 0   | 2   |
  | $T_4$ | 2   | 1   | 1   | 3   |
  
  - **a)** *Available: $(0,3,0,1)$*
    
    - First $T_2$ can be serviced, after which $(3,1,2,1)$ is added to the available matrix
      
      - *Available: $(3,4,2,2)$*
    
    - Next, $T_1$ can be serviced, after which $(2,2,1,0)$ is added to the available matrix
      
      - *Available: $(5,6,3,2)$*
    
    - Next, $T_3$ can be serviced after which $(0,5,1,0)$ is added to the available matrix
      
      - *Available: $(5,11,4,2)$*
    
    - Next, neither $T_0$ nor $T_4$ can be serviced since they both request 3 of resource $D$ and only 2 are available. Thus, the system is in an *unsafe state*
  
  - **b)** *Available: $(1,0,0,2)$*
    
    - First, $T_1$ can be serviced after which $(2,2,1,0)$ will be added to the available matrix
      
      - *Available: $(3,2,1,2)$*
    
    - Next, $T_2$ can be serviced after which $(3,1,2,1)$ will be added to the available matrix
      
      - *Available: $(6,3,3,3)$*
    
    - Next, $T_3$ can be serviced after which $(0,5,1,0)$ will be added to the available matrix
      
      - *Available: $(6,8,4,3)$*
    
    - Next, $T_4$ can be serviced after which $(4,2,1,2)$ will be added to the available matrix
      
      - *Available: $(10,10,5,5)$*
    
    - Finally, $T_0$ will be serviced after which $(3,0,1,4)$ will be added to the available matrix and now all threads have completed
      
      - *Available: $(13,10,6,9)$*
    
    - Thus, the system is in a *safe state*
